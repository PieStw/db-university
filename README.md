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

```

# Selezionare tutti i corsi di laurea magistrale

```sql

```

# Da quanti dipartimenti è composta l'università?

```sql

```

# Quanti sono gli insegnanti che non hanno un numero di telefono?

```sql

```

# Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

```sql

```

# Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

```sql

```

# Eliminare dalla tabella studenti il record creato precedentemente al punto 9

```sql

```

#

#
