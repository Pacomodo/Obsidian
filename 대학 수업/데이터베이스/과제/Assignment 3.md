1. 다음에 제시되어 있는 관계형 스키마를 토대로 테이블(table)들을 생성하여라. \[create table .......\] (테이블 생성시 primary key와 foreign key를 정의해야 하며 각 애트리뷰트의 타입은 임의대로 정의하여 사용하시오) \[각각의 “create table .......”과 “describe table”실행화면 제시함\] ※ 답안 작성 요령 3. 참고

	* classes (**class**, type, numGuns, displacement)
		* “class”는 새로운 급의 군함이 만들어졌을 때 그 급을 나타내기 위하여 붙여지는 명칭이다. 예를 들어 광개토대왕함이 만들어지고 난 후 이와 유사한 규모의 군함이 만들어 지면 그 군함을 “광개토대왕함급”이라고 class 명을 붙이게 된다.
		* “type”은 군함의 기능을 나타내는 것으로 전함(BB), 순양함(CC), 구축함(DD), 호위함(FF) 등이 있다.
		* “numGuns”는 해당 군함에 설치된 함포의 수를 나타내며, “displacement”는 군함의 배수량(주로 ton수로 표기)을 나타낸다.
	* ships (**s-name**, class, country, launched)
		* “s-name”은 군함의 이름(예를 들어, 독도함), “country”는 해당 군함을 보유하고 있는 국가명, “launched”는 해당 군함이 취역한 년도를 나타냄.
	* battles (**b-name**, year)
		* “b-name”은 해전명을 “year”는 해전이 발발한 년도를 나타냄.
	* outcomes (**s-name, b-name**, result)
		* 해당 군함(s-name)이 특정 해전(b-name)에 참여한 내역을 결과(result : 침몰, 손상, OK 등)와 함께 나타내는 릴레이션임.

```sql
create table classes (
    class  varchar(20) primary key,
    type char(7),
    numGuns int check (numGuns >= 0),
    displacement int check (displacement >= 0)
) engine = InnoDB;
```
![[Pasted image 20240508213428.png]]
```sql
create table ships (
	s_name varchar(20) primary key,
	class varchar(20) not null,
	country varchar(20),
	launched int check (launched >= 0),
	foreign key (class) references classes(class)
	on delete restrict
	on update cascade
) engine = InnoDB;
```
![[Pasted image 20240508213707.png]]
```sql
create table battles (
	b_name varchar(20) primary key,
	year int check (year >= 0)
) engine = InnoDB;
```
![[Pasted image 20240508214017.png]]
```sql
create table outcomes (
	s_name varchar(20),
	b_name varchar(20),
	result char(5),
	primary key (s_name, b_name),
	foreign key (s_name) references ships(s_name)
	on delete restrict
	on update cascade,
	foreign key (b_name) references battles(b_name)
	on delete restrict
	on update cascade
) engine = InnoDB;
```
![[Pasted image 20240508214612.png]]

2. 1.에서 생성한 테이블들 각각에 아래 조건에 부합하는 샘플 데이터(최소 5개 이상)들을 입력하고 각 테이블에 입력된 데이터를 출력(결과 화면)하여 제시하시오.

조건 : 샘플 데이터들은 “3. SQL 작성 문제”에 대한 답으로 작성한 SQL의 실행 결과가 “Empty set"이 아닌 결과가 나오도록 만들어야 함. ※ 답안 작성 요령 4. 참고

```sql
insert into classes (class, type, numGuns, displacement) values ('이순신', 'DD', 100, 6000);
insert into classes (class, type, numGuns, displacement) values ('을지문덕', 'BB', 70, 5000);
insert into classes (class, type, numGuns, displacement) values ('광개토대왕', 'FF', 10, 2300);
insert into classes (class, type, numGuns, displacement) values ('일성', 'DD', 30, 2500);
insert into classes (class, type, numGuns, displacement) values ('정일', 'CC', 50, 3000);
insert into classes (class, type, numGuns, displacement) values ('정은', 'FF', 5, 1500);
insert into classes (class, type, numGuns, displacement) values ('도쿄', 'DD', 80, 4900);
insert into classes (class, type, numGuns, displacement) values ('홋카이도', 'BB', 75, 3000);
insert into classes (class, type, numGuns, displacement) values ('요코하마', 'FF', 15, 2100);
insert into classes (class, type, numGuns, displacement) values ('베이징', 'DD', 80, 4500);
insert into classes (class, type, numGuns, displacement) values ('상하이', 'BB', 90, 4000);
insert into classes (class, type, numGuns, displacement) values ('광저우', 'CC', 20, 2400);
```

![[Pasted image 20240509031752.png]]

![[Pasted image 20240509031823.png]]


```sql
insert into ships (s_name, class, country, launched) values ('거북선', '이순신', '대한민국', 1595);
insert into ships (s_name, class, country, launched) values
('General Lee', '이순신', '대한민국', 1908);
insert into ships (s_name, class, country, launched) values ('문덕', '을지문덕', '대한민국', 1598);
insert into ships (s_name, class, country, launched) values ('문덕2', '을지문덕', '대한민국', 1910);
insert into ships (s_name, class, country, launched) values ('장군', '광개토대왕', '대한민국', 1925);

insert into ships (s_name, class, country, launched) values ('요코이치', '요코하마', '일본', 1590);
insert into ships (s_name, class, country, launched) values ('요코니', '요코하마','일본', 1591);
insert into ships (s_name, class, country, launched) values ('요코산', '요코하마','일본', 1592);
insert into ships (s_name, class, country, launched) values ('요코시', '요코하마','일본', 1593);
insert into ships (s_name, class, country, launched) values ('뉴요코', '요코하마','일본', 1920);
insert into ships (s_name, class, country, launched) values ('뉴도쿄', '도쿄','일본', 1905);
insert into ships (s_name, class, country, launched) values ('백설', '홋카이도','일본', 1935);

insert into ships (s_name, class, country, launched) values ('대성1', '일성','북한', 1970);
insert into ships (s_name, class, country, launched) values ('대성2', '정일','북한', 2000);
insert into ships (s_name, class, country, launched) values ('대성3', '정은','북한', 2010);

insert into ships (s_name, class, country, launched) values ('북경1', '베이징','중국', 1911);
insert into ships (s_name, class, country, launched) values ('북경2', '베이징','중국', 1912);
insert into ships (s_name, class, country, launched) values ('북경3', '베이징','중국', 1913);
insert into ships (s_name, class, country, launched) values ('상해1', '상하이','중국', 1914);
insert into ships (s_name, class, country, launched) values ('상해2', '상하이','중국', 1915);
insert into ships (s_name, class, country, launched) values ('상해3', '상하이','중국', 1916);
insert into ships (s_name, class, country, launched) values ('광주1', '광저우','중국', 1917);
insert into ships (s_name, class, country, launched) values ('광주2', '광저우','중국', 1918);
insert into ships (s_name, class, country, launched) values ('광주3', '광저우','중국', 1919);

```

![[Pasted image 20240509032615.png]]
![[Pasted image 20240509032638.png]]
![[Pasted image 20240509033144.png]]
![[Pasted image 20240509033453.png]]
![[Pasted image 20240509033922.png]]
![[Pasted image 20240509033938.png]]

```sql
insert into outcomes (s_name, b_name, result) values ('General Lee','1차','OK');
insert into outcomes (s_name, b_name, result) values ('General Lee','2차','OK');
insert into outcomes (s_name, b_name, result) values ('General Lee','3차','OK');
insert into outcomes (s_name, b_name, result) values ('General Lee','4차','OK');
insert into outcomes (s_name, b_name, result) values ('General Lee','5차','OK');

insert into outcomes (s_name, b_name, result) values ('요코이치','노량','침몰');
insert into outcomes (s_name, b_name, result) values ('요코니','노량','침몰');
insert into outcomes (s_name, b_name, result) values ('요코산','명량','침몰');
insert into outcomes (s_name, b_name, result) values ('요코시','명량','침몰');
insert into outcomes (s_name, b_name, result) values ('거북선','명량','OK');
insert into outcomes (s_name, b_name, result) values ('거북선','노량','OK');
insert into outcomes (s_name, b_name, result) values ('문덕','노량','손상');

insert into outcomes (s_name, b_name, result) values ('문덕2','1차','손상');
insert into outcomes (s_name, b_name, result) values ('문덕2','2차','손상');

insert into outcomes (s_name, b_name, result) values ('뉴도쿄','1차','손상');
insert into outcomes (s_name, b_name, result) values ('뉴도쿄','2차','침몰');

insert into outcomes (s_name, b_name, result) values ('북경1','3차','손상');
insert into outcomes (s_name, b_name, result) values ('상해1','3차','손상');
insert into outcomes (s_name, b_name, result) values ('광주1','3차','손상');
insert into outcomes (s_name, b_name, result) values ('북경1','4차','손상');
insert into outcomes (s_name, b_name, result) values ('상해1','4차','손상');
insert into outcomes (s_name, b_name, result) values ('광주1','4차','손상');
insert into outcomes (s_name, b_name, result) values ('북경1','5차','침몰');
insert into outcomes (s_name, b_name, result) values ('상해1','5차','침몰');
insert into outcomes (s_name, b_name, result) values ('광주1','5차','침몰');

```
![[Pasted image 20240509034315.png]]
![[Pasted image 20240509034842.png]]
![[Pasted image 20240509035216.png]]
![[Pasted image 20240509035648.png]]
![[Pasted image 20240509035706.png]]
```sql
insert into battles (b_name, year) values ('노량', 1598);
insert into battles (b_name, year) values ('명량', 1597);
insert into battles (b_name, year) values ('1차', 1910);
insert into battles (b_name, year) values ('2차', 1920);
insert into battles (b_name, year) values ('3차', 1930);
insert into battles (b_name, year) values ('4차', 1940);
insert into battles (b_name, year) values ('5차', 1945);
```
![[Pasted image 20240508225313.png]]


3. 다음 질의어를 SQL로 작성하고 그 결과를 출력(결과 화면)하여 제시하시오. (※ 답안 작성 요령 5. 참고)

(1) '노량' 해전에서 '침몰'된 군함의 보유 국가명을 찾아라.

```sql
select distinct country
from ships
where s_name in (
select s_name
from outcomes
where b_name = '노량' and result = '침몰'
);
```
![[Pasted image 20240509040751.png]]

(2) 취역한 년도에 해전에 참전하여 ‘손상’을 당한 군함의 이름을 찾아라.
```sql
select s_name
from outcomes natural join ships natural join battles 
where result = '손상' and launched = year;
```
![[Pasted image 20240509042641.png]]

(3) 가장 많은 함포를 보유하고 있는 군함의 이름(class)을 찾아라. (nested subquery 이용)
```sql
select class
from classes
where numGuns >= all (select numGuns from classes);
```
![[Pasted image 20240509044931.png]]

(4) “대한민국”이 보유하고 있는 군함들의 이름들을 찾되 해당 군함들이 참전한 기록이 있다면 참전한 해전명을 함께 찾아라.
```sql
select s_name, b_name
from (select s_name from ships where country = '대한민국') as S natural left outer join outcomes;
```
![[Pasted image 20240509050713.png]]

(5) 국가별 보유 군함의 수와 총배수량을 구하여라(aggregate function을 이용).
```sql
select country, count(s_name), sum(displacement)
from ships natural join classes
group by country;
```
![[Pasted image 20240509052326.png]]

(6) 다섯 번 이상 해전에 참전한 군함을 보유한 국가명을 찾아라.
```sql
select distinct country
from ships
where s_name in (
select s_name
from outcomes
group by s_name
having count(b_name) >= 5
);
```
![[Pasted image 20240509053954.png]]

(7) “1945”에 발발한 해전에 참전한 군함의 이름과 취역년도(launched)를 찾아라.
```sql
select distinct s_name, launched
from ships
where s_name in (
select s_name
from outcomes
where b_name in (
select b_name
from battles
where year = 1945
)
);
```
![[Pasted image 20240509055046.png]]

(8) 해전에 참여한 이력이 없는 군함의 이름을 찾아라.
```sql
select s_name
from ships
where s_name not in (select s_name from outcomes);
```
![[Pasted image 20240509055345.png]]

(9) ‘노량해전’과 ‘명량해전’에 모두 참여한 군함의 이름을 찾아라. (nested subquery 이용)
```sql
select s_name
from outcomes
where b_name = '노량' and s_name in (
select s_name
from outcomes
where b_name = '명량'
);
```
![[Pasted image 20240509060420.png]]

(10) 배수량(displacement)이 5000톤보다 큰 모든 급(class)의 군함을 보유하고 있는 국가명(country)을 찾아라.

문제의 해석이 모호해서 2가지 버전의 답안을 남깁니다.
1. '모든'이라는 말을 단순히 배수량이 5000톤 보다 큰 'class'가 여러 개 있다는 뜻을 강조하는 것으로 간주하여, 배수량이 5000톤 초과인 군함을 하나라도 보유하고 있다면, 그 국가를 찾는 것. 
```sql
select distinct country
from ships
where class in (
select class
from classes
where displacement > 5000
);
```
![[Pasted image 20240509062613.png]]
2. 배수량 5000톤 이상 군함을 종류별로 최소 한 척씩은 가지고 있는 국가를 찾으라는 뜻으로 해석.
```sql
select distinct country
from ships natural join classes
where displacement > 5000
group by country
having count(distinct class) = 
(select count(distinct class) from classes where displacement > 5000);
```
![[Pasted image 20240509063821.png]]

데이터를 삽입했었을 때는 배수량 5000톤 이상인 클래스를 '이순신' 클래스 하나만 정의했었고, 이 클래스의 군함을 가지는 국가를 대한민국으로 유일하게 설정했기 때문에 결과가 같게 나왔습니다.

하지만 배수량 5000톤 이상인 클래스를 여러 개 설정하고, 이 클래스에 해당하는 군함을 가지는 국가 또한 다양하게 설정한다면 결과는 다르게 나올 것입니다.