1. Contare quanti iscritti ci sono stati ogni anno
    - SELECT COUNT(*) AS 'numero_iscritti', YEAR(`enrolment_date`) AS 'anno_iscrizione' FROM `students` GROUP BY YEAR(`enrolment_date`);
2.  