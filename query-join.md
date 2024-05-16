1.  Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
    - SELECT `students`.* FROM `degrees` INNER JOIN `students` ON `degrees`.`id` = `students`.`degree_id` WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

2.  Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
Neuroscienze
    - SELECT `degrees`.* FROM `departments` INNER JOIN `degrees` ON `departments`.`id` = `degrees`.`department_id` WHERE `departments`.`name` = 'Dipartimento di Neuroscienze' AND `degrees`.`level` = 'magistrale';
