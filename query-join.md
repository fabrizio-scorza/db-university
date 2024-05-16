1.  Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
    - SELECT `students`.* FROM `degrees` INNER JOIN `students` ON `degrees`.`id` = `students`.`degree_id` WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

2.  Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
    - SELECT `degrees`.* FROM `departments` INNER JOIN `degrees` ON `departments`.`id` = `degrees`.`department_id` WHERE `departments`.`name` = 'Dipartimento di Neuroscienze' AND `degrees`.`level` = 'magistrale';

3.  Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
    - SELECT `courses`.* FROM `teachers` INNER JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id` INNER JOIN `courses` ON `courses`.`id` = `course_teacher`.`course_id` WHERE `teachers`.`id` = 44;

4.  Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
    - SELECT `students`.`surname`, `students`.`name`, `degrees`.`name` AS 'degree_name', `degrees`.`level`, `departments`.`name` AS 'department_name' FROM `students` INNER JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id` INNER JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` ORDER BY `students`.`surname` ASC;

5.  Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
    - SELECT `degrees`.`name` AS 'degree_name', `degrees`.`level`, `courses`.`name` AS 'course_name', `courses`.`period`, `courses`.`year`, `courses`.`cfu`, `teachers`.`name` AS 'teacher_name', `teachers`.`surname` FROM `degrees` INNER JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id` INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id` INNER JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`;

6.  Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
    - SELECT DISTINCT `teachers`.* FROM `departments` INNER JOIN `degrees` ON `departments`.`id` = `degrees`.`department_id` INNER JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id` INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id` INNER JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id` WHERE `departments`.`name` = 'Dipartimento di Matematica';
