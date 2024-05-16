1. Contare quanti iscritti ci sono stati ogni anno
    - SELECT COUNT(*) AS 'numero_iscritti', YEAR(`enrolment_date`) AS 'anno_iscrizione' FROM `students` GROUP BY YEAR(`enrolment_date`);

2.  Contare gli insegnanti che hanno l'ufficio nello stesso edificio
    - SELECT COUNT(*) AS 'numero_insegnanti', `office_address` AS 'ufficio' FROM `teachers` GROUP BY `office_address`;

3.  