I ATTACHED PREVIOUS COMMENTS AND I RESOLVED MY TASK AS PER DESCRIPTION.

COMMENTS: need to improve db design with more data and try to attach all the queries also


1.select * from users
 
2.ALTER TABLE users ADD Email varchar(20);

3.UPDATE users SET Email = 'tamizh123@gmail.com' where CandName='Tamizh';

4.DELETE FROM users WHERE Email='tamizh123@gmail.com';

5.INSERT INTO users(CandName, Age,Course, Task, Attendence, Email)
VALUES ('lokesh', '29', 'sap', 'pending', 'present', 'lok123@gmail.com');

6.SELECT * FROM users
LIMIT 3;

7.SELECT * FROM users
ORDER BY age;

8.SELECT MIN(Age) AS youngage
FROM users;
