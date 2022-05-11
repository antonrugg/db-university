1) SELECT * FROM `students` WHERE `date_of_birth` >= '1990-01-01' AND `date_of_birth` < '1991-01-01';  
2) SELECT * FROM `courses` WHERE `cfu` > 10;  
3) SELECT `name`, TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) AS `age` FROM `students` WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) >= 30;
4) SELECT * FROM `courses` WHERE `period` = 'I semestre' AND `year` = 1;  
5) SELECT * FROM `exams` WHERE `hour` > '14:00:00' AND `date` = '2020-06-20';  
6) SELECT * FROM `degrees` WHERE `level` = 'magistrale';  
7) SELECT * FROM `departments`;  
8) SELECT COUNT(id) FROM `teachers` WHERE `phone` IS NULL;  
