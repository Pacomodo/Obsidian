### 조인이란?

- 여러 테이블의 데이터를 질의할 경우 사용
- 하나 이상의 테이블이나 뷰의 데이터를 로우로 결합하여 검색
- 일반적인 경우 Primary key나 Foreign key 값의 연관에 의해 조인이 성립

### 표준화된 JOIN(ANSI JOIN)

- `FROM`절에서 바로 `JOIN`을 명시적으로 정의

```sql
SELECT table1.column, table2.column
FROM table1
[CROSS JOIN table2] |
[NATURAL JOIN table2] | 
[JOIN table2 USING (column_name)] |
[JOIN table2 ON (table1.column_name = table2.column_name)] |
[LEFT|RIGHT|FULL OUTER JOIN table2 ON (table1.column_name = table2.column_name)];
```

- `CROSS`는 쓸 일이 별로 없고, `NATURAL`은 권장 X(확장성 떨어짐)

### `CROSS JOIN`

- 두 테이블 상호간의 조합 생성
- 테이블 사이의 Cartesian Product.

### `NATURAL JOIN`

- 두 테이블에서 동일한 이름을 가진 모든 열을 기준으로 조인
- 두 테이블의 일치하는 모든 열에서 같은 값을 가진 행을 선택
- 조인조건으로 사용한 컬럼 앞에는 테이블 명이나 테이블 별칭 명시할 수 없다

확장성이 떨어지는 이유 :
ex) 예를 들어 `EMP`테이블에는 `ename, deptNo, a`라는 컬럼이 있고, `DEPT`테이블에는 `deptNo, dname, a`라는 컬럼이 있음.
나는 `deptNo`만을 기준으로 조인하고 싶은데 `NATURAL JOIN`은 `a`까지 포함해서 조인함

### `USING JOIN`

- 등가 조인에 특정 열을 지정할 수 있음
- `USING`절에 참조되는 열은 SQL문 어디에서도 테이블 이름이나 별칭을 가질 수 없다.

### `ON JOIN`

- 임의의 열을 지정하거나 조인할 열을 지정할 때 사용
- 조인 조건이 다른 검색조건과 분리된다.