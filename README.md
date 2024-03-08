I ATTACHED PREVIOUS COMMENTS AND I RESOLVED MY TASK AS PER DESCRIPTION.

COMMENTS: need to improve db design with more data and try to attach all the queries also


 select * from users
 
ALTER TABLE users ADD Email varchar(20);

UPDATE users SET Email = 'tamizh123@gmail.com' where CandName='Tamizh';

DELETE FROM users WHERE Email='tamizh123@gmail.com';

INSERT INTO users(CandName, Age,Course, Task, Attendence, Email)
VALUES ('lokesh', '29', 'sap', 'pending', 'present', 'lok123@gmail.com');

SELECT * FROM users
LIMIT 3;

SELECT * FROM users
ORDER BY age;

SELECT MIN(Age) AS youngage
FROM users;
