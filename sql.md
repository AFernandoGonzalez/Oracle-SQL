# Oracle SQL

### Order, Concat & Alias

- We can use pipes || to concatinate sentences.
```sql
select ENAME, SAL, DEPTNO from emp
order by deptno, sal desc

select 'Hi my name is ' || ENAME || ' makes $' || SAL || ' per month' as Employee_Income
```

### Single Row Function & Using Dual Table

- concatinating using CONCAT
```sql
select 'my name is ' || ename from emp

select concat('my name is ', ename) from emp
select concat('my name is ', ename) as "Sentence" from emp 

select upper(ename) from emp

select upper(ename) as "UpperCase_Name"
from emp
where deptno = 20

select upper('Hi')
from DUAL

select *
from DUAL

select 'pizza' as FOOD, 'fanta' as DRINK, concat('hi', ' Jonh') as "This is a func" from DUAL

select concat(lower(ename), ' is the name') as Sentence from emp

select concat(lower(ename), upper(' is the name')) as Two_Functions  from emp

select concat(concat(lower(ename), upper(' is the name ')), concat(lower(' and their job is: '), upper(job))) as Name_And_Job from emp

```