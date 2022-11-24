# Singel Row Functions (SRF)


-- resource
-- https://www.techonthenet.com/oracle/functions/index.php

```sql
select * from emp

-- lower case names from emp table
select lower(ename) from emp


-- single row functions (SRF) as part of the WHERE clause
select * from emp
where job = upper('manager');


-- string based functions
select initcap('Hi my name is Fer') as Capitalization
from dual

select length('my name is fer') as Length
from dual

select ename, length(ename) from emp
where length(ename) = 6

-- 3 args: what , start , extraction  
select substr(ename, 0) as extraction  from emp
select substr(ename, 0, 1) as extraction  from emp

select lpad(ename, 10, 'left') from emp
select rpad(ename, 10, 'right') from emp

select ltrim(ename, 'K') from emp
select rtrim(ename, 'G') from emp



-- numeric and date single row functions (SRFs)

select round(100.45, 1) as Rounded from dual
select round(100.54) as Rounded from dual

select trunc(190.3423423) from dual
select trunc(190.3423423, 2) from dual


select sysdate as Todays_Date from dual
select systimestamp as Todays_Date_Detailed from dual

select add_months('11/17/2012', 0) Monthss from dual
-- advance 2 months
select add_months('11/17/2012', 2) Monthss from dual
-- go back 2 months
select add_months('11/17/2012', -2) Monthss from dual
-- total months between 2 given dates
select months_between('12/17/2012', '10/17/2012') Months_Between from dual
select months_between('12/17/2012', '12/17/2012') Months_Between from dual

select trunc(systimestamp) from dual
select ename, hiredate,  trunc(hiredate, 'MONTH') as Truc_Date from emp



-- conversions and format dates
select sysdate from dual
select to_char(sysdate, 'mm-dd-yy') from dual

select * from emp
-- conver a number to string
select ename, sal, to_char(sal, '$99,999.99') as Salary_Converted from emp
-- conver a string to actual date number
select to_date('2012-08-23', 'yyyy-mm-dd') from dual

select to_date('3 of June, 2012', 'dd "of" Month, YYYY') from dual



select ename, sal, NVL(to_char(comm), 'no data found') from emp;

select ename, length(ename), NVL(nullif(to_char(length(ename)), to_char(5)), 'lenght is' ) from emp
where sal > 2000

```