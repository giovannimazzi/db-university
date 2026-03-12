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

```

3. Calcolare la media dei voti di ogni appello d'esame

```sql

```

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql

```
