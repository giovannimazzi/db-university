1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT
	students.*
FROM university.students
INNER JOIN university.degrees
ON students.degree_id = degrees.id
#WHERE degrees.id = 53; #id associato al Corso di Laurea in Economia
WHERE degrees.name LIKE "Corso di Laurea in Economia";
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
   Neuroscienze

```sql
SELECT
	degrees.*
FROM university.degrees
INNER JOIN university.departments
ON degrees.department_id = departments.id
WHERE
	degrees.level LIKE "magistrale" AND
    departments.name LIKE "Dipartimento di Neuroscienze";
```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT
	courses.*
FROM university.courses
JOIN university.course_teacher
ON courses.id = course_teacher.course_id
WHERE course_teacher.teacher_id = 44;

```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
   sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
   nome

```sql
SELECT
	students.*,
    `degrees`.`name` degree_name,
    `degrees`.`level` degree_level,
    `degrees`.`address` degree_address,
    `degrees`.`email` degree_email,
    `degrees`.`website` degree_website,
    `departments`.`name` department_name,
    `departments`.`address` department_address,
    `departments`.`phone` department_phone,
    `departments`.`email` department_email,
    `departments`.`website` department_website,
    `departments`.`head_of_department` head_of_department
FROM university.students
JOIN university.degrees
ON students.degree_id = degrees.id
JOIN university.departments
ON degrees.department_id = departments.id
ORDER BY students.surname, students.name;
```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
SELECT
	degrees.*,
    `courses`.`name` course_name,
    `courses`.`description` course_description,
    `courses`.`period` course_period,
    `courses`.`year` course_year,
    `courses`.`cfu` course_cfu,
    `courses`.`website` course_website,
    `teachers`.`name` teacher_name,
    `teachers`.`surname` teacher_surname,
    `teachers`.`phone` teacher_phone,
    `teachers`.`email` teacher_email,
    `teachers`.`office_address` teacher_office_address,
    `teachers`.`office_number` teacher_office_number
FROM university.degrees
JOIN university.courses
ON courses.degree_id = degrees.id
JOIN university.course_teacher
ON course_teacher.course_id = courses.id
JOIN university.teachers
ON course_teacher.teacher_id = teachers.id;
```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
   Matematica (54)

```sql

```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
   per ogni esame, stampando anche il voto massimo. Successivamente,
   filtrare i tentativi con voto minimo 18.

```sql

```
