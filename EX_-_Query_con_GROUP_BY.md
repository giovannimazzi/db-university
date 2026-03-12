1. Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT
	YEAR(students.enrolment_date) year,
	COUNT(students.id) enrolments
FROM university.students
GROUP BY YEAR(students.enrolment_date)
ORDER BY YEAR(students.enrolment_date) DESC;
```

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT
	teachers.office_address building,
	COUNT(teachers.id) number_of_teachers
FROM university.teachers
GROUP BY teachers.office_address;
```

3. Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT
	exam_student.exam_id exam_session,
    AVG(exam_student.vote) average_vote
FROM university.exam_student
GROUP BY exam_student.exam_id;
```

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT
	degrees.department_id department_id,
	COUNT(degrees.id) degrees
FROM university.degrees
GROUP BY degrees.department_id;
```

Soluzione alternativa esercizio 4:

```sql
SELECT
	departments.id department_id,
    departments.name department_name,
	COUNT(degrees.id) degrees
FROM university.degrees
INNER JOIN university.departments
ON degrees.department_id = departments.id
GROUP BY departments.id;
```
