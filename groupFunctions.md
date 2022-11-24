# Group Functions


```sql
SELECT avg(sal), job 
FROM emp
GROUP BY job

SELECT min(sal), job 
FROM emp
GROUP BY job


-- we cannot user WHERE Clause in a group functions

select count(*), job from emp
group by job
having count(*) > 3
order by job


select deptno, count(*) from emp 
group by deptno
having count(*) > 1



select deptno, job, count(*) as Total, sal from emp
group by job, deptno, sal


select job, deptno, count(*) as Total from emp
group by job, deptno


select * from dept
where deptno = (select deptno from dept where deptno = 30)


select * from dept
where deptno < (select deptno from dept where deptno = 30)
and dname = 'ACCOUNTING'

select * from dept
select * from (select * from dept)

select * from emp where deptno = ( select deptno from dept where loc = 'CHICAGO')

select * from dept
where deptno in (select deptno from dept where deptno in (10 ,20) )



select * from (select * from emp)
select job, ename, (select job from emp where ename = 'KING') from emp
where job = (select job from emp where job = 'PRESIDENT')