## Chapter 13. Data Storage Structures

>[!Problem]
>DB 응용 프로그램으로부터 데이터 블록을 요청 받았을 때 DB buffer manager가 이 요청을 처리하는 과정을 상세하게 설명하시오.

버퍼 매니저가 데이터 블록을 요청받은 경우, 해당하는 데이터 블록이 이미 메모리 내에 존재하는 지 버퍼를 검색합니다.
응용 프로그램이 요청한 데이터 블록이 이미 버퍼에 있는 경우, 버퍼 매니저는 메인 메모리에 있는 블록 주소를 응용 프로그램으로 전달해줍니다.
이때, 다른 응용프로그램들이 데이터 블록을 내보내게 된다면 잘못된 주소를 반환할 수 있으므로, 이를 방지하기 위해 블록을 고정시키기도 합니다.
응용 프로그램이 요청한 데이터 블록이 버퍼에 존재하지 않는 경우, 버퍼 매니저는 요청한 데이터 블록의 할당을 위해 공간을 만듭니다.
만약 메모리의 부족으로 인해 데이터 블록의 할당을 위한 공간을 만들 수 없는 경우, 기존에 존재하던 블록을 버려서 공간을 할당합니다.
기존에 존재하던 블록이 전과 이전과 비교했을 때 업데이트가 된 상태라면, 그 블록을 디스크에 작성해야 합니다.
그런 다음에 버퍼 매니저는 요청한 데이터 블록을 디스크에서 버퍼로 가져오고, 데이터 블록의 메인 메모리 주소를 응용 프로그램에게 전달하는 역할을 합니다.

디스크에서 버퍼로 데이터를 가져오는 작업은 코스트가 많이 드는 작업이기 때문에, 효율적인 DBMS구동을 위해, 기존에 존재하던 블록을 버려서 공간을 할당하는 데에는 전략적인 접근이 필요합니다.
이를 Buffer Replacement Policy라고 합니다.
대표적으로 LRU(Least recently used)Strategy가 있습니다.
이 전략은 지금까지 가장 나중에 사용된 데이터 블록이 앞으로도 잘 사용되지 않을 것 이라는 가정 하에서 진행되는 전략입니다.
따라서, 기존에 존재하던 블록을 버릴 때에는 지금까지 가장 적게 사용된 데이터 블록을 버립니다.

select *
from instructor $\bowtie$ department;

다음과 같은 쿼리를 아래와 같은 의사코드로 처리하는 과정을 생각해봅시다.
```
for each tuple ins of instructor:
    for each tuple dept of department:
        if tuple ins and dept match:
        ...
```
department 튜플이 포함된 블록을 생각해봅시다.
instructor relation의 각 튜플에 대해 모든 department 튜플 블록을 한 번씩 검사해야 합니다. department 블록의 처리가 완료되면 다른 모든 department 블록이 처리될 때까지 해당 블록에 다시 접근하지 않는다는 것을 알고 있습니다.
따라서 가장 최근에 사용된 department 블록은 다시 보게 될 때까지 오래 걸리고, 가장 나중에 사용된 department 블록이 다음에 보게 될 블록이 됩니다.
따라서 이 경우 LRU Strategy를 사용하면 비효율적이게 됩니다. 이런 경우 MRU(Most recently used) Strategy를 사용하면 효율적이게 됩니다.
실제 DB Buffer manager는 이러한 전략들을 혼합해서 사용하고, 데이터들의 통계 데이터(Meta data)를 활용하여 어떠한 블록을 버릴 지 효율적으로 골라냅니다.

## Chapter 15-16. Query Processing & Query Optimization

>[!note] Problem
>(1) Equivalence rule 들 중 세 가지를 선택하여 각 rule들이 타당함을 예(예제 릴레이션)를 들어 증명하시오. (Equivalence rules은 p747~752 참고)
>(2) “logical query execution plan”과 “physical query execution plan”의 차이점을 비교 설명하시오.

###### (1)
Rule 1. Conjunctive selection operations can be deconstructed into a sequence of individual selections. This transformation is referred to as a cascade of $\sigma$.
$$
\sigma_{\theta_{1} \land \theta_{2}}(E) = \sigma_{\theta_{1}}(\sigma_{\theta_{2}}(E))
$$
Relation Customer가 다음과 같이 주어져 있다고 가정해봅시다.
![[Pasted image 20240410060710.png|center|400]]
$$
\begin{align}
& \sigma_{\text{customer\_city = Rye}\land \text{customer\_name = Curry}}(\text{customer}) \\
=& \ \sigma_{\text{customer\_city = Rye}}(\sigma_{\text{customer\_name = Curry}} (\text{customer})) \\
=& \ \text{(Curry, North, Rye)}
\end{align}
$$
따라서 성립함을 쉽게 확인할 수 있습니다.

Rule 2. Selection operations are commutative.
$$
\sigma_{\theta_{1}}(\sigma_{\theta_{2}}(E)) = \sigma_{\theta_{2}}(\sigma_{\theta_{1}}(E))
$$
위의 예시를 그대로 사용하면 다음과 같습니다.
$$
\begin{align}
& \ \sigma_{\text{customer\_city = Rye}}(\sigma_{\text{customer\_name = Curry}} (\text{customer})) \\
=& \ \text{(Curry, North, Rye)} \\
& \ \sigma_{\text{customer\_name = Curry}}(\sigma_{\text{customer\_city = Rye}} (\text{customer})) \\
=& \ \sigma_{\text{customer\_name = Curry}}(\text{(Curry, North, Rye)},\text{(Smith, North, Rye)}) \\
=& \ \text{(Curry, North, Rye)}
\end{align}
$$
따라서 같음을 확인할 수 있습니다.

Rule 3.  The projection operation distributes over the union operation
$$
\Pi_{L}(E_{1} \cup E_{2}) = \Pi_{L}(E_{1}) \cup \Pi_{L}(E_{2})
$$
provided $E_{1}$ and $E_{2}$ have the same schema.
위의 Relation Customer에, 아래와 같은 Relation Customer2가 있다고 가정해봅시다.

| customer_name | customer_street | customer_city |
| :-----------: | :-------------: | :-----------: |
|     John      |      Alma       |   Palo Alto   |
|     Jacob     |     Senator     |   Brooklyn    |
|     David     |      Park       |  Pittsfield   |
|     Jude      |      Park       |  Pittsfield   |
|     Lily      |     Spring      |  Pittsfield   |
|     Bella     |     Spring      |  Pittsfield   |
|    Johnson    |      Alma       |   Palo Alto   |

$\text{customer}\cup \text{customer2}$는 다음과 같습니다.

| customer_name | customer_street | customer_city |
| :-----------: | :-------------: | :-----------: |
|     John      |      Alma       |   Palo Alto   |
|     Jacob     |     Senator     |   Brooklyn    |
|     David     |      Park       |  Pittsfield   |
|     Jude      |      Park       |  Pittsfield   |
|     Lily      |     Spring      |  Pittsfield   |
|     Bella     |     Spring      |  Pittsfield   |
|    Johnson    |      Alma       |   Palo Alto   |
|     Adams     |     Spring      |  Pittsfield   |
|    Brooks     |     Senetor     |   Brooklyn    |
|     Curry     |      North      |      Rye      |
|     Glenn     |    Sand Hill    |   Woodside    |
|     Green     |     Walnut      |   Stamford    |
|     Hayes     |      Main       |   Harrison    |
|     Jones     |      Main       |   Harrison    |
|   Lindsday    |      Park       |  Pittsfield   |
|     Smith     |      North      |      Rye      |
|    Turner     |     Putnam      |   Stamford    |
|   Williams    |     Nassau      |   Princeton   |
따라서, $\Pi_{\text{customer\_city}}(\text{customer}\cup \text{customer2})$는 다음과 같습니다.

| customer_city |
| :-----------: |
|  Pittsfield   |
|   Brooklyn    |
|      Rye      |
|   Woodside    |
|   Stamford    |
|   Harrison    |
|   Prinston    |
|   Palo Alto   |
$\Pi_{\text{customer\_city}}(\text{customer})$ 는 다음과 같습니다.

| customer_city |
| :-----------: |
|  Pittsfield   |
|   Brooklyn    |
|      Rye      |
|   Woodside    |
|   Stamford    |
|   Harrison    |
|   Prinston    |
|   Palo Alto   |
$\Pi_{\text{customer\_city}}(\text{customer2})$ 는 다음과 같습니다.

| customer_city |
| :-----------: |
|   Palo Alto   |
|   Brooklyn    |
|  Pittsfield   |
따라서, $\Pi_{\text{customer\_city}}(\text{customer}) \cup \Pi_{\text{customer\_city}}(\text{customer2})$은 다음과 같습니다.

| customer_city |
| :-----------: |
|  Pittsfield   |
|   Brooklyn    |
|      Rye      |
|   Woodside    |
|   Stamford    |
|   Harrison    |
|   Prinston    |
|   Palo Alto   |
따라서, 같음을 확인할 수 있습니다.
###### (2)
Logical query execution plan은 DBMS와는 독립적인 반면, Physical query execution plan은 DBMS에 종속적입니다. 즉, Logical query execution plan은 실제 DBMS가 어떻게 이를 실행할 지는 고려하지 않습니다. 반면, Physical query execution plan은 실제 DBMS가 어떻게 이를 실행할 지를 고려합니다. 예를 들어, 같은 Logical query가 주어진다고 할 지라도, 실제 그 연산이 DBMS상에서 어떻게 작동하는지는 다양한 방법으로 구현돼 있고, 실제 데이터의 저장 위치 등도 고려하기 때문에, 이를 실행하는 Physical query execution plan은 여러 가지로 다를 수 있습니다.
따라서, Logical query execution 면에서는 코스트가 낮은 plan이 Physical query execution 면에서는 코스트가 높은 plan이 될 수 있습니다.
Physical query execution plan optimization을 진행할 때에는 하나의 Logical query에 대해서 다양한 실행 방법들을 염두해 둡니다. Logical query execution plan optimization을 진행할 때에는 데이터들의 크기와 같은 Metadata를 활용하여 실제 실행하지 않고 간략하게 Equivalent한 다른 logical query execution plan들의 코스트를 계산합니다.
## Chapter 17. Transactions

>[!note] Problem 17.8
>The **lost update** anomaly is said to occur if a transaction $T_j$ reads a data item, then another transaction $T_k$ writes the data item (possibly based on a previous read), after which $T_j$ writes the data item.
>The update performed by $T_k$ has been lost, since the update done by $T_j$ ignored the value written by $T_k$.
>
>a. Give an example of a schedule showing the lost update anomaly.
>b. Give an example schedule to show that the lost update anomaly is possible with the **read committed** isolation level.
>c. Explain why the lost update anomaly is not possible with the **repeatable read** isolation level.

###### (a)
Lost update Problem은 다음과 같은 예시에서 발생할 수 있습니다.

| $T_{1}$  | $T_{2}$  |
| :------: | :------: |
| read(A)  |          |
|          | read(A)  |
|          | write(A) |
| write(A) |          |
이 예시를 보면, $T_{1}$이 먼저 데이터 A를 읽고, 그 후에 $T_{2}$가 데이터 A를 읽습니다.
곧바로 $T_{2}$는 A를 업데이트합니다.
이후 $T_{1}$은 업데이트 된 데이터 A가 아닌, 이전에 읽었던 데이터 A를 기반으로 데이터 A를 업데이트합니다.
이 경우, 트랜잭션 $T_{2}$가 진행했던 업데이트 작업은 $T_{1}$에 의해 사라지게(**Lost**)됩니다. 이러한 문제를 Lost update Problem 이라고 부릅니다.

###### (b)
Read committed isolation level에서도 이러한 Lost update problem은 발생할 수 있습니다.
예를 들어, 위의 예시를 변형하여 가져와 봅시다.

| $T_{1}$  | $T_{2}$  |
| :------: | :------: |
| read(A)  |          |
|          | read(A)  |
|          | write(A) |
|          | commited |
| write(A) |          |
| commited |          |
이 예시에서 맨 처음에 $T_{1}$과 $T_{2}$가 모두 커밋된 데이터 A를 읽었다고 가정합시다.
$T_{2}$는 커밋된 데이터 A를 읽고 곧바로 그 데이터를 변경한 후 커밋합니다.
$T_{1}$은 이전에 읽었던 데이터 A를 기반으로 데이터 변경을 진행합니다.
물론 $T_{1}$이 읽었었던 데이터는 당시 시점으로 보았을 때 커밋된 데이터였으므로 문제가 없습니다.
이후 $T_{1}$이 커밋하게 되면, $T_{2}$가 진행했던 업데이트 작업은 여전히 $T_{1}$에 의해 사라지게 됩니다.
하지만 이 과정에서 $T_{1}$과 $T_{2}$ 모두 커밋된 데이터만 읽었으므로, Read commited isolation level이 보장되게 됩니다.

###### (c)
Repeatable read isolation level에서는 Lost update problem이 발생하지 않습니다.
Repeatable read가 보장되기 위해서는 한 트랜잭션에서 어떤 데이터를 읽을 때 그 데이터가 다른 트랜잭션에 의해 변경되지 않아야 합니다.

이는 2-phase locking protocol에 의해 수행되어질 수 있습니다.
어떤 트랜잭션 $T$가 어떤 데이터 A를 변경하기 위해서는 가장 먼저 그 데이터에 대한 Exclusive lock을 concurrency control manager에게 요청해야 합니다.
Concurrency control manager가 그 lock을 승인하면, 그 데이터는 2-phase locking protocol에 의해 더 이상 $T$가 데이터 A를 접근하지 않을 때까지 lock이 걸리게 됩니다.
따라서 다른 트랜잭션이 데이터 A를 변경할 수 없으므로, repeatable read가 보장됩니다.

위의 예시라면, $T_{1}$은 데이터 A를 읽기 위해 Shared lock을 요청합니다.
Concurrency control manager는 이를 승인하여, $T_{1}$이 read(A) 작업을 수행할 수 있습니다.
이후에도 여전히 $T_{1}$은 데이터 A에 대해 접근하고 있으므로, unlock작업을 하지 않습니다.
이후 $T_{2}$는 데이터 A를 읽기 위해 concurrency control manager에게 Shared lock을 요청합니다.
이를 승인하여, $T_{2}$는 read(A)작업을 수행할 수 있습니다.
이후 $T_{2}$는 write(A) 작업을 수행하기 위해 concurrency control manager에게 Exclusive lock을 요청합니다.
하지만 $T_{1}$이 이미 Shared lock을 보유하고 있으므로 이는 거절당합니다.
따라서 데이터 A는 $T_{2}$에 의해 변경되지 않습니다.

>[!note] Problem 17.20
>For each of the following isolation levels, give an example of a schedule that respects the speciﬁed level of isolation but is not serializable:
>
>a. Read uncommitted
>b. Read committed

###### (a)
Read uncommited isolation level을 갖추고 동시에 serializable 하지 않은 가장 간단한 예시는 다음과 같습니다.

| $T_{1}$  | $T_{2}$  |
| :------: | :------: |
| read(A)  |          |
| write(A) |          |
|          | read(A)  |
|          | write(A) |
| read(A)  |          |
|          |  commit  |
|  commit  |          |
이 경우, $T_{1}$이 $T_{2}$에서 변경된 데이터 A를 커밋되지 않은 상태에서 읽었으므로, read uncommited isolation level을 만족함을 알 수 있습니다.
또한, $T_{1}$이 두 번째로 읽은 데이터 A는 $T_{2}$에 의해 변경된 데이터이고, $T_{2}$가 처음 읽은 데이터 A는 $T_{1}$에 의해 변경된 데이터이므로, 이 예시는 serializable 하지 않음을 확인할 수 있습니다.

###### (b)
Read commited isolation level을 갖추고 동시에 serializable 하지 않은 가장 간단한 예시는 다음과 같습니다.

|  $T_{1}$  |  $T_{2}$  |
| :-------: | :-------: |
| lock-s(A) |           |
|  read(A)  |           |
| unlock(A) |           |
|           | lock-x(A) |
|           | write(A)  |
|           | unlock(A) |
|           |  commit   |
| lock-s(A) |           |
|  read(A)  |           |
| unlock(A) |           |
|  commit   |           |
$T_{2}$에서 exclusive lock을 걸음으로써 다른 트랜잭션에서 데이터 A를 접근할 수 없기 때문에 트랜잭션 $T_{2}$가 커밋될 때 까지 데이터 A를 접근하여 읽는 것을 방지할 수 있습니다.
따라서, 이 예시는 read commited를 보장합니다.
반면, $T_{1}$에서 처음 읽는 데이터 A와 $T_{1}$에서 나중에 읽는 데이터 A는 $T_{2}$에 의해 달라진다는 점을 확인할 수 있습니다.
따라서, 이 예시는 serializable하지 않음을 확인할 수 있습니다.

## Chapter 18. Concurrency Control 

>[!note] Problem 18.3
>What beneﬁt does rigorous two-phase locking provide? How does it compare with other forms of two-phase locking?

기본적으로, rigorous two-phase locking은 strict two-phase locking의 엄격한 버전이기 때문에, strict two-phase locking이 가지고 있는 장점들을 가지고 있습니다.
Strict two-phase locking이 가지는 장점은 Problem 18.17에 쓰여있습니다.

Rigorous two-phase locking은 어떤 트랜잭션이 커밋되기 직전까지 데이터에 대한 모든 lock을 풀지 않는 two-phase locking입니다.
Rigorous two-phase locking에 따르면, 트랜잭션 $T_{1}$이 데이터 A에 대해서 Shared lock을 가지고 있는 경우, 다른 트랜잭션 $T_{2}$가 데이터 A를 읽을 수만 있습니다.
$T_{1}$이 데이터 A에 대해 Exclusive lock을 가지고 있는 경우, 다른 트랜잭션은 $T_{1}$이 커밋되기 전 까지 데이터 A에 접근할 수 없습니다.

따라서, 데이터를 변경하지 않고 단순히 읽는 것은 serializable에 위배되지 않으므로, 트랜잭션이 커밋되는 순으로 트랜잭션을 쉽게 serialized 할 수 있다는 장점이 있습니다.

>[!note] Problem 18.17
>What beneﬁt does strict two-phase locking provide? What disadvantages result?

Two-phase locking protocol에서 유의해야 할 사항은, unlock 시점에 관한 것입니다.
Unlock은 항상 커밋 직전에만 이루어지는 것이 아닙니다.
다시 말하자면, unlock을 한 뒤 곧 이어 커밋이 이루어지는 것이 아닙니다.
그로 인해,  Cascading rollback problem이 생길 수 있습니다.
예를 들어, 다음과 같은 상황을 살펴봅시다.

|    $T_{1}$     |  $T_{2}$  |  $T_{3}$  |
| :------------: | :-------: | :-------: |
|   lock-x(A)    |           |           |
|    read(A)     |           |           |
|   lock-s(B)    |           |           |
|    read(B)     |           |           |
|    write(A)    |           |           |
|   unlock(A)    |           |           |
|                | lock-x(A) |           |
|                |  read(A)  |           |
|                | write(A)  |           |
|                | unlock(A) |           |
|                |           | lock-s(A) |
|                |           |  read(A)  |
| $T_{1}$ fails. |           |           |

모든 트랜잭션들이 two-phase locking protocol을 따라감은 쉽게 확인할 수 있습니다.
이 상황을 살펴보면, $T_{1}$이 커밋되지 않은 상태에서 $T_{2}$와 $T_{3}$가 동시에 진행되었고, 그 과정에서 $T_{1}$가 어떠한 이유로 인해 실패되었습니다.
따라서, $T_{1}$를 롤백 해야만 하는데, 그로 인해 $T_{2}$와 $T_{3}$또한 롤백을 해야만 하는 상황에 처해있습니다.
왜냐하면, $T_{2}$와 $T_{3}$는 모두 $T_{1}$이 변경 작업을 한 데이터 A를 다루었기 때문입니다.

Strict two-phase locking은 기존 two-phase locking에 한 가지 제한조건을 더 걺으로써 Cascading rollback problem을 해결하였습니다.
그 제한 조건은, 어떠한 트랜잭션이 가지고 있는 Exclusive lock들은 모두 그 트랜잭션의 커밋 시점에 unlock하는 것입니다.
이로 인해, 어떠한 트랜잭션 $T$가 데이터 A에 대해서 변경 작업을 하고 있는 경우, 다른 트랜잭션은 $T$가 커밋되기 전까지는 데이터 A를 다룰 수 없게 됩니다.
따라서 위의 예시에서 언급했던 문제를 해결할 수 있습니다.

따라서, strict two-phase locking은, 기존 two-phase locking이 가지고 있는 장점인 serializability에, cascading rollback problem을 해결함으로써 데이터 복구에 더 용이하다는 장점을 더했습니다.

반면, 기존 two-phase locking에 비해 트랜잭션의 concurrency를 줄였다는 점이 단점입니다. 또한, 기존 two-phase locking이 가지고 있는 교착 상태 문제(deadlock problem)을 해결할 수 없었다는 것이 단점입니다.


>[!note] Problem 18.18
> Most implementations of database systems use strict two-phase locking. Suggest three reasons for the popularity of this protocol.

strict two-phase locking이 자주 쓰이는 이유를 3가지 정도로 생각해보면 다음과 같습니다.

* 다른 locking protocol에 비해, exclusive lock을 커밋 시점에 한 번에 unlock하기만 하면 되므로, 비교적 구현하기 쉽습니다.
* 물론, 모든 lock을 커밋 시점에 한 번에 unlock하는 rigorous two-phase locking보다는 구현기 어렵지만, Concurrency관점에서 볼 때 rigorous two-phase locking보다 유하다는 장점 있습니다. 즉, 적절한 concurrency를 가지고 있다고 판단할 수 있습니다.
* 위에서 언급했던 것처럼, Cascading rollback problem을 해결함으로써, 복구에 용이하다 장점이 있습니다.

## Chapter 19. Recovery

>[!note] Problem 19.2
> Explain the purpose of the checkpoint mechanism. How often should checkpoints be performed? How does the frequency of checkpoints aﬀect:
> 
> - System performance when no failure occurs?
> - The time it takes to recover from a system crash?

체크포인트 메커니즘의 근본적인 목적은 시스템 Failure가 발생했을 때 진행해야 하는 Redo 연산의 감소입니다.
예를 들어, 어떤 시스템이 1초에 20000번의 트랜잭션을 수행할 수 있다고 가정합시다.
한 트랜잭션 당 두 번의 write연산을 수행한다고 가정합시다.
그렇다면 1초에 약 $40000$번의 로그가 남는다고 생각할 수 있습니다.
이 시스템이 1년 동안 문제 없이 작동되다가, 1년 째 되는 날에 시스템 Failure가 났다고 가정합시다.
우리는 데이터 스토리지(Disk)에 언제, 어떠한 데이터 블록의 정보가 갱신되었는지 알 수 없으므로, 로그 스토리지에 저장된 로그에 따라 Redo연산을 진행해 주어야 합니다.
그 Redo연산의 양은, 약 $365\times 24 \times 60 \times 60 \times 40000$ $=$ $1261440000000 \approx 1.26 \times 10^{12}$번이므로, 매우 오랜 시간이 소요됨을 확인할 수 있습니다.
중간에 체크포인트 메커니즘을 수행한다면, 이러한 Redo연산 양을 줄일 수 있습니다.

Failure가 자주 발생하는 환경이라면 체크포인트는 자주 수행되야 좋을 것입니다.
그렇지 않는 안정된 환경이라면 체크포인트는 자주 수행할 필요가 없습니다.

체크포인트 메커니즘은 자주 수행되면 자주 수행될 수록, 시스템 Failure가 발생하지 않는다는 가정 하에서, 전체적인 시스템 퍼포먼스가 낮아질 것입니다.
체크포인트 메커니즘을 수행하면, 현재 진행되는 모든 트랜잭션을 중단하고, 지금까지 수행했던 모든 트랜잭션에 대한 로그들을 로그 버퍼에서 로그 스토리지로 옮깁니다.
이후, 모든 변경된 데이터 블록들을 데이터 베이스 버퍼에서 데이터 스토리지로 옮깁니다.
우리는 시스템 Failure가 발생하지 않는다는 가정 하에서 논의하는 것이기 때문에, 이 메커니즘이 자주 반복될 수록, 데이터 베이스 버퍼에서 데이터 스토리지로 기록하는 시간이 추가 되므로, 시스템 퍼포먼스 면에서 낮아질 것이라는 예상을 할 수 있습니다.

반면, 시스템 Failure가 발생한다는 가정 하에서 체크포인트 메커니즘을 자주 수행 하게 된다면 Redo연산이 그만큼 줄어들게 되므로, 시스템 Crash로부터의 복구 시간이 빠를 것입니다.