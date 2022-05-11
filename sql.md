1) SELECT * FROM `students` WHERE `date_of_birth` >= '1990-01-01' AND `date_of_birth` < '1991-01-01';  
2) SELECT * FROM `courses` WHERE `cfu` > 10;  
3) SELECT `name`, TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) AS `age` FROM `students` WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) >= 30;
4) SELECT * FROM `courses` WHERE `period` = 'I semestre' AND `year` = 1;  
5) SELECT * FROM `exams` WHERE `hour` > '14:00:00' AND `date` = '2020-06-20';  
6) SELECT * FROM `degrees` WHERE `level` = 'magistrale';  
7) SELECT * FROM `departments`;  
8) SELECT COUNT(id) FROM `teachers` WHERE `phone` IS NULL;  


-----------------GROUP BY------------------  

1) SELECT COUNT(*), YEAR(`enrolment_date`) FROM `students` GROUP BY YEAR(`enrolment_date`);

2) SELECT COUNT(*), `office_address` FROM `teachers` GROUP BY `office_address`;

3) SELECT AVG(vote), `exam_id` FROM `exam_student` GROUP BY `exam_id`;

4) SELECT COUNT(`id`), `department_id` FROM `degrees` GROUP BY `department_id`;



-----------QUERY CON JOIN--------  

1) SELECT `students`.`name`, `surname`, `fiscal_code`, `degrees`.`name` FROM `students` INNER JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id` WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

2) SELECT `degrees`.`name`, `degrees`.`level` FROM `degrees` INNER JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` WHERE `degrees`.`level` = 'magistrale' AND `departments`.`name` = 'Dipartimento di Neuroscienze';

3) SELECT `courses`.`name` FROM `courses`
INNER JOIN `course_teacher`
ON `courses`.`id`= `course_teacher`.`course_id`
INNER JOIN `teachers`
ON `teachers`.`id` = `course_teacher`.`teacher_id`
WHERE `teachers`.`id` = 44;

4) SELECT `students`.`name`, `students`.`surname`, `degrees`.`name`, `departments`.`name`
FROM `students`
INNER JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`
INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`id`
ORDER BY `students`.`surname` ASC, `students`.`name` ASC;

5) SELECT `degrees`.`name` AS 'Corso di Laurea', `courses`.`name` AS 'Materia del corso', `teachers`.`surname`, `teachers`.`name` FROM `degrees`
INNER JOIN `courses`
ON `courses`.`id` = `degrees`.`id`
INNER JOIN `teachers`
ON `teachers`.`id` = `courses`.`degree_id`;

6) SELECT `teachers`.`name`, `teachers`.`surname` FROM `teachers`
INNER JOIN `course_teacher`
ON `course_teacher`.`teacher_id` = `teachers`.`id`
INNER JOIN `courses` 
ON `course_teacher`.`course_id` = `courses`.`id`
INNER JOIN `degrees`
ON `courses`.`degree_id` = `degrees`.`id`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = 'Dipartimento di Matematica';

7) 

