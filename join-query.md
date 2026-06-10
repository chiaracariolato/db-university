#Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SELECT *
FROM students as s
JOIN degrees ON s.degree_id = degrees.id
WHERE degrees.name like "Corso di laurea in Economia";

#Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
SELECT * 
FROM departments
JOIN degrees ON departments.id = degrees.department_id
WHERE departments.name LIKE "Dipartimento di Neuroscienze" AND degrees.level LIKE "magistrale";

#Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
SELECT c.* 
FROM courses AS c
JOIN course_teacher AS ct ON c.id = ct.course_id
JOIN teachers AS t ON t.id = ct.teacher_id
WHERE t.id = 44;

#Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e 
#il relativo dipartimento, in ordine alfabetico per cognome e nome
SELECT *
FROM students AS s
JOIN degrees AS d ON d.id = s.degree_id
JOIN departments AS de ON de.id = d.department_id
ORDER BY s.surname, s.name ;

#Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
SELECT *
FROM degrees as d
JOIN courses as c ON d.id = c.degree_id
JOIN course_teacher as ct ON c.id = ct.course_id
JOIN teachers as t ON t.id = ct.teacher_id
ORDER BY d.name;

#Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica
SELECT t.name, t.surname
FROM teachers AS t
JOIN course_teacher as ct ON t.id = ct.teacher_id
JOIN courses AS c ON c.id = ct.course_id
JOIN degrees AS d ON c.degree_id = d.id
JOIN departments AS de ON de.id = d.department_id
WHERE de.id=5
group by t.id
order by t.id;

#BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, 
#stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.
SELECT s.id, s.name, s.surname, c.id AS course_id,
COUNT(*) AS numero_tentativi,
MAX(es.vote) AS voto_massimo
FROM students AS s
JOIN exam_student AS es ON es.student_id = s.id
JOIN exams AS e ON e.id = es.exam_id
JOIN courses AS c ON c.id = e.course_id
GROUP BY s.id, c.id
HAVING max(es.vote) >= 18;