# mySQL_task

`CREATE TABLE users (id int PRIMARY KEY,student_name varchar(45), student_email varchar(40));
INSERT INTO users VALUES (1,'Abhinav','Abhinav@mail.com'),(2,'Mohammed', 'Mohammed@mail.com'),(3,'Akanksha', 'Akanksha@mail.com'),(4,'Arya', 'Arya@mail.com'),(5,'Gopi','Gopi@mail.com');
CREATE TABLE codekata (student_id int,problems int);
INSERT INTO codekata VALUES (1,150),(2,100),(3,200),(4,170),(5,160);
CREATE TABLE attendance (student_id int,attended int);
INSERT INTO attendance VALUES (1,60),(2,75),(3,65),(4,80),(5,95);
CREATE TABLE topics (id int PRIMARY KEY,topic_name text not null);
INSERT INTO topics VALUES(1,'HTML'),(2,'CSS'),(3,'JS'),(4,'ReactJS'),(5,'NodeJS');
CREATE TABLE tasks(id int PRIMARY KEY,task_name text not null);
INSERT INTO tasks VALUES(1,'WebPage'),(2,'CSS Card'),(3,'JS pagination'),(4,'React Frontend'),(5,'NodeJS Backend');
CREATE TABLE company_drives (student_id int NOT NULL, name text not null);
INSERT INTO company_drives VALUES(1,'Google'),(1,'Amazon'),(2,'Facebook'),(3,'Razor Pay'),(4,'JusPay'),(2,'Google'),(3,'Amazon'),(3,'Facebook'),(5,'Razor Pay'),(5,'JusPay');
CREATE TABLE mentors (id int PRIMARY KEY, mentor_name TEXT  not null, topic_id int);
INSERT INTO mentors VALUES (1,'Rajavasanthan',4),(2,'Rajavasanthan',5),(3,'Venkat',1),(4,'Venkat',2),(5,'Ragav',3);
CREATE TABLE courses (id int PRIMARY KEY, name TEXT NOT NULL);
INSERT INTO courses VALUES (1,'HTML&CSS'),(2, 'JavaScript'),(3, 'ReactJS'),(4,'NodeJS'),(5,'MongoDB');
CREATE TABLE student_activated_courses (student_id int not null, course_id int NOT NULL);
INSERT INTO student_activated_courses VALUES (1,1),(1,3),(2,1),(3,4),(3,5),(4,3),(5,1),(5,2);`

`select SUM(problems) as Solved from codekata;
SELECT student_name,COUNT(name) as Companies_Attended FROm company_drives INNER JOIn users ON company_drives.student_id=users.id GROUP by id;
SELECT * FROM student_activated_courses INNER JOIN courses on student_activated_courses.course_id=courses.id;
SELECT mentor_name, topic_name as Mentor FROM mentors inner JOIN topics on topics.id=mentors.topic_id;
SELECT mentor_name,COUNT(student_id) AS Students_assigned FROM student_activated_courses INNER JOIN mentors ON student_activated_courses.topics=mentors.topic_id GROUP BY mentor_name;`
