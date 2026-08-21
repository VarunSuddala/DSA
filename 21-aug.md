## Question 1: 
Frog Jump Problem description A frog moves through indexed stones with given heights. It may jump one or two positions and pays the absolute height difference. 
Find minimum total energy.  
Input 
  format n followed by n heights.  
Output 
  format Print the minimum energy.
# code
```python
n=int(input())
heights = list(map(int,input().split()))

dp=[0]*(n)

dp[0]=heights[0]
dp[1]= abs(heights[0]-heights[1])

for i in range (2,n):
    one = dp[i-1]+abs(heights[i-1]-heights[i])
    two =dp[i-2]+abs(heights[i-2]-heights[i])
    
    dp[i]=min(one,two)
    
print(dp[n-1])

```
---
## Question 2: 
Frog Jump with K Distances Problem description The frog may jump from a stone to any of the next k stones. 
Each jump costs the absolute height difference. Minimize total energy.  
Input 
  format n k, then n heights.  
Output 
  format Print minimum energy.
# code
```python
```
---
*`SQL JOIN Practice`*:
---
```sql
1
select e.emp_id, e.emp_name, d.dept_name, d.location from employees e inner join departments d on e.dept_id = d.dept_id;
2
select e.emp_id, e.emp_name, d.dept_name from employees e left join departments d on e.dept_id = d.dept_id;
3
select d.dept_id, d.dept_name from departments d left join employees e on d.dept_id = e.dept_id where e.emp_id is null;
4
select e.emp_name, p.project_name, d.dept_name, ep.hours from employees e
inner join employee_project ep on e.emp_id = ep.emp_id
inner join projects p on ep.project_id = p.project_id
inner join departments d on p.dept_id = d.dept_id;
5
select p.project_id, p.project_name, e.emp_name from projects p left join employee_project ep
on p.project_id = ep.project_id left join employees e
on ep.emp_id = e.emp_id;
6
select e.emp_name as employee_name, m.emp_name as manager_name from employees e left join employees m
on e.manager_id = m.emp_id;
7
select e.emp_id, e.emp_name, count(ep.project_id) as total_projects from employees e
inner join employee_project ep on e.emp_id = ep.emp_id
group by e.emp_id, e.emp_name having count(ep.project_id) > 1;
8
select d.dept_name, count(e.emp_id) as employee_count, avg(e.salary) as average_salary
from departments d left join employees e on d.dept_id = e.dept_id
group by d.dept_id, d.dept_name;
```

