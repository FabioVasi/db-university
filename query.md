SELECT date_of_birth FROM `students` WHERE YEAR(date_of_birth) = 1990;
## first query solved filter year of birth result (160)


SELECT cfu FROM `courses` WHERE cfu > 10;
## second query couses with cfu > 10 result (479)


SELECT date_of_birth FROM `students` WHERE TIMESTAMPDIFF(YEAR, date_of_birth, CURRENT_DATE) > 30;
## third query select students over 30 years old result (3468)


SELECT period, year FROM `courses` WHERE period = 'I semestre' AND year = '1';
## fourth query select all courses from 'I semestre' and 'anno 1' result (286)


SELECT hour, date FROM `exams` WHERE HOUR(hour) >= '14' AND date = '2020-06-20';
## fifth query exams with hours >= 14 and date = 2020-06-20 result (21)


SELECT level FROM `degrees` WHERE level = 'magistrale';
## sixth query select all magistral degree result (38)


SELECT COUNT(id) AS total_departments FROM departments;
## seventh query total count of departments result (12)


SELECT phone FROM `teachers` WHERE phone IS null;
## last query count of teachers without a phone number result (50)






## Group by:
## Contare quanti iscritti ci sono stati ogni anno result (709 first year, 608 second year)
SELECT COUNT(*) AS `student_count`, YEAR(`enrolment_date`)
FROM `students`
GROUP BY YEAR(`enrolment_date`);


## Contare gli insegnanti che hanno l'ufficio nello stesso edificio result (29)
SELECT COUNT(*) AS `address_count`, `office_address`
FROM `teachers`
GROUP BY `office_address`;


## Calcolare la media dei voti di ogni appello d'esame
LECT COUNT(`exam_id`) AS `exams_count`, AVG(`vote`) AS `average_vote` 
FROM `exam_student` 
GROUP BY `exam_id`;


## Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT COUNT(*) AS `degrees_count`, `department_id`, `departments`.`name` AS `department_name`
FROM `degrees`
JOIN `departments` ON `department_id` = `departments`.`id`
GROUP BY `department_id`;