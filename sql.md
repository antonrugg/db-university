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

1)

