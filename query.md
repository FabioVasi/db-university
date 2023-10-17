SELECT date_of_birth FROM `students` WHERE YEAR(date_of_birth) = 1990;
-- first query solved filter year of birth result (160)


SELECT cfu FROM `courses` WHERE cfu > 10;
-- second query couses with cfu > 10 result (479)


SELECT date_of_birth FROM `students` WHERE TIMESTAMPDIFF(YEAR, date_of_birth, CURRENT_DATE) > 30;
-- third query select students over 30 years old result (3468)


SELECT period, year FROM `courses` WHERE period = 'I semestre' AND year = '1';
-- fourth query select all courses from 'I semestre' and 'anno 1' result (286)


SELECT hour, date FROM `exams` WHERE HOUR(hour) >= '14' AND date = '2020-06-20';
-- fifth query exams with hours >= 14 and date = 2020-06-20 result (21)


SELECT level FROM `degrees` WHERE level = 'magistrale';
-- sixth query select all magistral degree result (38)


SELECT COUNT(id) AS total_departments FROM departments;
-- seventh query total count of departments result (12)


SELECT phone FROM `teachers` WHERE phone IS null;
-- last query count of teachers without a phone number result (50)