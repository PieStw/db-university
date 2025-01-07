# Selezionare tutti gli studenti nati nel 1990

```sql
SELECT *
FROM university.students
WHERE YEAR(date_of_birth) = 1990;
```

# Selezionare tutti i corsi che valgono più di 10 crediti

```sql
SELECT * FROM university.courses
WHERE cfu > 10;
```

# Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT * FROM university.students
WHERE 2025 - YEAR(date_of_birth) > 30;
```

# Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea

```sql
SELECT * FROM university.courses
WHERE period = "I semestre";
```

# Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020

```sql
SELECT * FROM university.exams
WHERE date(date) = "2020-06-20" and hour(hour) > 14;
```

# Selezionare tutti i corsi di laurea magistrale

```sql
SELECT * FROM university.degrees
WHERE level = "magistrale";
```

# Da quanti dipartimenti è composta l'università?

```sql
SELECT COUNT(*) FROM university.departments;
```

# Quanti sono gli insegnanti che non hanno un numero di telefono?

```sql
SELECT COUNT(*) FROM university.teachers
WHERE phone is null;
```

# Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

```sql
???
```

# Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

```sql
???
```

# Eliminare dalla tabella studenti il record creato precedentemente al punto 9

```sql
???
```

# Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT COUNT(*) FROM university.students
group by(year(enrolment_date));
```

# Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT COUNT(*) FROM university.teachers
group by(office_address);
```

# Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT avg(vote) FROM university.exam_student
group by(exam_id);
```

# Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT COUNT(*) FROM university.degrees
group by(department_id);
```
