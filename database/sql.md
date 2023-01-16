# SQL 문법

## **테이블 만들기 CREATE**

```sql
CREATE TABLE customers (id INTEGER PRIMARY KEY, name TEXT, age INTEGER, weight REAL);
```

#### AUTOINCREMENT

id 값에 AUTOINCREMENT를 붙여주면 1씩 증가하는 값이 자동으로 생성된다

```sql
CREATE TABLE books (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    author TEXT,
    title TEXT,
    words INTEGER);
```

## 데이터 삽입 INSERT

```sql
INSERT INTO customers VALUES (73, "Brian", 33);
```

#### 특정 열

```sql
INSERT INTO customers (name, age) VALUES ("Brian", 33);
```

## **데이터 쿼리**

### 선택

#### 전체 선택

```sql
SELECT * FROM customers; 
```

#### 특정 열 선택

```sql
SELECT name, age FROM customers;
```

### 조건 필터링

#### 조건으로 필터링 WHERE

```sql
SELECT * FROM customers WHERE age > 21;
```

#### 그룹화된 것을 조건으로 필터링 HAVING

WHERE와 헷갈리지 않도록 주의!

```sql
SELECT type, SUM(calories) AS total_calories FROM exercise_logs
    GROUP BY type
    HAVING total_calories > 150
    ;
```

#### 다중 조건 필터링 AND OR

```sql
SELECT * FROM customers WHERE age < 21 AND state = "NY";
```

#### IN으로 필터링

특정 값이 리스트에 존재하는지 찾아준다

```sql
SELECT * FROM customers WHERE plan IN ("free", "basic");
```

반대의 결과를 찾고 싶다면 NOT IN

```sql
SELECT * FROM exercise_logs WHERE type NOT IN ("biking", "hiking", "tree climbing", "rowing");
```

### 서브 쿼리

외부 쿼리 안에서 작동하는 쿼리

```sql
SELECT * FROM exercise_logs WHERE type IN (
    SELECT type FROM drs_favorites);
```

```sql
SELECT * FROM exercise_logs WHERE type IN (
    SELECT type FROM drs_favorites WHERE reason LIKE "%cardiovascular%");
```

해당 단어가 포함된 모든 결과를 찾을 땐 양옆에 `%` 기호를 붙여주고 앞에 `LIKE`

### CASE

```sql
SELECT name, 
	CASE 
		WHEN age > 18 THEN "adult" 
		ELSE "minor" 
	END "type" 
FROM customers;
```

```sql
SELECT COUNT(*),
    CASE 
        WHEN heart_rate > 220-30 THEN "above max"
        WHEN heart_rate > ROUND(0.90 * (220-30)) THEN "above target"
        WHEN heart_rate > ROUND(0.50 * (220-30)) THEN "within target"
        ELSE "below target"
    END as "hr_zone"
FROM exercise_logs
GROUP BY hr_zone;
```

## 데이터 집계

### 집계 함수

#### 최대값MAX, 최소값MIN, 합SUM, 평균AVG

```sql
SELECT MAX(age) FROM customers;
```

### 데이터 그룹화 GROUP BY

```sql
SELECT gender, COUNT(*) FROM students GROUP BY gender;
```

### 결과 정렬 ORDERD BY

```sql
SELECT * FROM customers WHERE age > 21 ORDER BY age DESC;
```

### 횟수 COUNT 를 구하기

어떤 열이든 상관없기에 `*` 을 넣은 것.

```sql
SELECT type FROM exercise_logs GROUP BY type HAVING COUNT(*) >= 2;
```

## 관계형 테이블에 조인

### Inner Join

내부 조인은 두 테이블에서 일치하는 기록으로만 행을 생성한다

```sql
SELECT customers.name, orders.item 
	FROM customers 
	JOIN orders 
	ON customers.id = orders.customer_id;
```

```sql
/* explicit inner join - JOIN */
SELECT students.first_name, students.last_name, students.email, student_grades.test, student_grades.grade FROM students
    JOIN student_grades
    ON students.id = student_grades.student_id
    WHERE grade > 90;
```

### Outer Join

LEFT OUTER JOIN 왼쪽 테이블에서 모든 데이터를 가져오라는 뜻. 왼쪽 테이블의 모든 걸 유지한 채 오른쪽과 결합한다.

LIGHT도 있으며 단순히 정반대의 기능을 할 뿐이다.

FULL OUTER JOIN은 왼쪽 오른쪽 모두에서 일치하는 행을 찾고 둘 다 못 찾으면 NULL

```sql
SELECT customers.name, orders.item 
	FROM customers 
	LEFT OUTER JOIN orders 
	ON customers.id = orders.customer_id;
```

### Self Join

구분을 위해 별명을 붙여준다. 양쪽 다 해도 되고 한쪽만 해도 되고

```sql
SELECT students.first_name, students.last_name, buddies.email as buddy_email
    FROM students
    JOIN students buddies
    ON students.buddy_id = buddies.id;
```

### 여러 결합 합쳐서 사용하기

ON 구문을 각각의 결합에 사용해야 한다.

```sql
SELECT a.title, b.title FROM project_pairs
    JOIN student_projects a
    ON project_pairs.project1_id = a.id
    JOIN student_projects b
    ON project_pairs.project2_id = b.id;
```

## 데이터 다루기

### 업데이트와 삭제

#### UPDATE 갱신

id로 지정하는 것이 가장 안전하다

```sql
UPDATE customers SET age = 33 WHERE id = 73;
```

```sql
UPDATE diary_logs SET content = "I had a horrible fight with OhNoesGuy" WHERE id = 1;
```

#### DELETE 삭제

```sql
DELETE FROM customers WHERE id = 73;
```

### ALTER TABLE 테이블 생성 후 변경

#### 새로운 열 추가

default를 지정하면 NULL 대신 나올 기본값을 설정할 수 있다

```sql
ALTER TABLE diary_logs ADD emotion TEXT default "unknown";
```

#### TABLE RENAME

```sql
ALTER TABLE travel_spots RENAME TO places_to_live;
```

***

### REF

* [https://ko.khanacademy.org/computing/computer-programming/sql/sql-basics/pt/creating-a-table-and-inserting-data](https://ko.khanacademy.org/computing/computer-programming/sql/sql-basics/pt/creating-a-table-and-inserting-data)
