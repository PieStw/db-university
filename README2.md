# Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT `s`.* FROM `university`.`students` AS `s`
JOIN `university`.`degrees` AS `d`
ON `s`.`degree_id` = `d`.`id`
WHERE `d`.`id` = 53;
```

# Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```sql
SELECT `d`.* FROM `university`.`degrees` AS `d`
JOIN `university`.`departments` AS `dep`
ON `d`.`department_id` = `dep`.`id`
WHERE `d`.`level` = "magistrale" AND `dep`.`id` = 7;
```

# Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT `c`.* FROM `university`.`course_teacher` AS `ct`
JOIN `university`.`courses` as `c`
ON `ct`.`course_id` = `c`.`id`
WHERE `ct`.`teacher_id` = 44
```

# Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql
SELECT * FROM `university`.`students` AS `s`
JOIN `university`.`degrees` AS `d`
ON `s`.`degree_id` = `d`.`id`
JOIN `university`.`departments` AS `dep`
ON `d`.`department_id` = `dep`.`id`
ORDER BY `s`.`surname` , `s`.`name`;
```

# Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
SELECT `c`.*, `d`.`name`, `t`.`name`, `t`.`surname` FROM `university`.`courses` AS `c`

JOIN `university`.`degrees` AS `d`
ON `c`.`degree_id` = `c`.`id`

JOIN `university`.`course_teacher` AS `ct`
ON `c`.`id` = `ct`.`course_id`

JOIN `university`.`teachers` AS `t`
ON `t`.`id` = `ct`.`teacher_id`;
```

# Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql
SELECT `t`.* FROM `university`.`teachers` AS `t`

JOIN `university`.`course_teacher` AS `ct`
ON `t`.`id` = `ct`.`teacher_id`

JOIN `university`.`courses` AS `c`
ON `c`.`id` = `ct`.`course_id`

JOIN `university`.`degrees` AS `d`
ON `d`.`id` = `c`.`degree_id`

JOIN `university`.`departments` AS `dep`
ON `d`.`department_id` = `dep`.`id`

WHERE `dep`.`id` = 5;
```

# BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

```sql
SELECT count(*) FROM `university`.`students` AS `s`

JOIN `university`.`exam_student` AS `es`
ON `s`.`id` = `es`.`student_id`
WHERE `es`.`vote` > 18
GROUP BY `s`.`id`;
```
