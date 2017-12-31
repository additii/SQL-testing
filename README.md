# SQL-testing

/*Complex SQL Queries Interview Questions & Answers
https://www.wisdomjobs.com/e-university/complex-sql-queries-interview-questions.html */


//Query To Find Second Highest Salary Of Employee?
Select distinct Salary from Employee e1 where 2=Select count(distinct Salary) from Employee e2 where e1.salary<=e2.salary;

//Query To Find Duplicate Rows In Table?
Select * from Employee a where row_id != select max(row_id) for Employee b where a.Employee_num=b.Employee_num;

//How To Fetch Monthly Salary Of Employee If Annual Salary Is Given?
Select Employee_name,Salary/12 as ‘Monthly Salary’ from employee;

//What Is The Query To Fetch First Record From Employee Table?
Select * from Employee where Rownum =1;

//What Is The Query To Fetch Last Record From The Table?
Select * from Employee where Rowid= select max(Rowid) from Employee;

//What Is Query To Display First 5 Records From Employee Table?
Select * from Employee where Rownum <= 5;

//What Is Query To Display Last 5 Records From Employee Table?
Select * from Employee e where rownum <=5

Union:

select * from (Select * from Employee e order by rowid desc) where rownum <=5;

//What Is Query To Display Nth Record From Employee Table?
Select * from Employee  where rownum = &n;

//How To Get 3 Highest Salaries Records From Employee Table?
select distinct salary from employee a where 3 >= (select count(distinct salary) from emp loyee b where a.salary <= b.salary) order by a.salary desc;

//How To Display Odd Rows In Employee Table?
Select * from(Select rownum as rno,E.* from Employee E) where Mod(rno,2)=1;


 

//How To Display Even Rows In Employee Table?
Select * from(Select rownum as rno,E.* from Employee) where Mod(rno,2)=0;

//How To Fetch 3rd Highest Salary Using Rank Function?
select * from (Select Dense_Rank() over ( order by  salary desc) as Rnk,E.* from Employee E) where Rnk=3;

//How Can I Create Table With Same Structure Of Employee Table?
Create table Employee_1 as Select * from Employee where 1=2;

//Display First 50% Records From Employee Table?
Select rownum,E.* from Employee E where rownum<=(Select count(*/2) from Employee);

//Display Last 50% Records From Employee Table?
Select rownum,E.* from Employee E

Minus

Select rownum,E.* from Employee E where rownum<=(Select count(*/2) from Employee);

//How Can I Create Table With Same Structure With Data Of Employee Table?
Create table Employee1 as select * from Employee;

//How Do I Fetch Only Common Records Between 2 Tables?
Select * from Employee;

Intersect

Select * from Employee1;

//Find Query To Get Information Of Employee Where Employee Is Not Assigned To The Department.?
Select * from Employee where Dept_no Not in(Select Department_no from Employee);

//How To Get Distinct Records From The Table Without Using Distinct Keyword?
select * from Employee a where  rowid = (select max(rowid) from Employee b where  a.Employee_no=b.Employee_no);


 

Select All Records From Employee Table Whose Name Is ‘amit’ And ‘pradnya’.
Select * from Employee where Name in(‘Amit’,’Pradnya’);

Select All Records From Employee Table Where Name Not In ‘amit’ And ‘pradnya’?
select * from Employee where name Not  in (‘Amit’,’Pradnya’);
