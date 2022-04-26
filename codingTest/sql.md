## SQL 문제
### QUESTION DESCRIPTION
A university maintains data on professors, departments, courses, and schedules in four tables:
DEPARTMENT, PROFESSOR, COURSE, and SCHEDULE.

Write a query to print the names of professors with the names of the courses they teach
(or have taught) outside of their department. Each row in the results must be distinct (i.e., a professor teaching the same course over multiple semesters should only appear once), but the results can be in any order.
Output should contain two columns: PROFESSOR.NAME, COURSE.NAME .
<img width="480" alt="스크린샷 2022-04-26 오후 10 38 20" src="https://user-images.githubusercontent.com/87690768/165312768-b3672559-dafb-4cef-80a1-281c69c326ca.png">

### Given Data
Omitted

### Sample Output
Antonio Rodriguez Astronomy
Harry Myers Earth Sciences
Nancy Daniels Materials Science and Metallurgy
Gloria Vasquez Materials Science and Metallurgy
Antonio Rodriguez Geography
Daniel Gilbert Earth Sciences
Matthew Stevens Applied Mathematics and Theoretical Physics
Nancy Daniels Pure Mathematics and Mathematical Statistics
Nancy Daniels Applied Mathematics and Theoretical Physics
Nancy Daniels Materials Science and Metallurgy

### Explanation
By referring to the sample data above, we can confirm that:
1. Professor Antonio Rodriguez's department_id is 3, but the Astronomy course's department_id is 1.
2. Professor Harry Myers's department_id is 4, but the Earth Sciences course's department_id is 1.
3. Professor Nancy Daniels's department_id is 4, but the Astronomy course's department_id is 1.
4. Professor Gloria Vasquez's department_id is 4, but the Materials Science and Metallurgy course's department_id is 1.
5. Professor Antonio Rodriguez's department_id is 3, but the Geography course's department_id is 1.
6. Professor Daniel Gilbert's department_id is 5, but the Earth Sciences course's department_id is 1.
7. Professor Matthew Stevens's department_id is 2, but the Applied Mathematics and Theoretical Physics course's department_id is 1.
8. Professor Nancy Daniels's department_id is 4, but the Pure Mathematics and Mathematical Statistics course's department_id is 1.
9. Professor Nancy Daniels's department_id is 4, but the Applied Mathematics and Theoretical Physics course's department_id is 1.
10. Professor Nancy Daniels's department_id is 4, but the Materials Science and Metallurgy course's department_id is 1.

### 내 풀이
~~~sql
SELECT DISTINCT p.name AS professor_name, c.name AS course_name
FROM professor p JOIN schedule s
ON s.professor_id = p.id
JOIN course c
ON s.course_id = c.id
WHERE c.department_id <> p.department_id;
~~~

