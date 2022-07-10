# Cornell-SQL-Examples

Here are several of the SQL Queries I created completing the Data Science SQL and Tableau Certificate through Cornell University in August of 2022.

SELECT A.first_name, A.last_name, B.race_name, C.race_position
...
FROM Runners AS A
INNER JOIN Registrations AS B
ON A.runner_id = B.runner_id
INNER JOIN Results AS C
ON B.registration_id = C.registration_id
WHERE C.race_position = (SELECT MIN(race_position)
FROM Registrations
INNER JOIN Results
ON Registrations.registration_id = Results.registration_id
WHERE Registrations.race_name = B.race_name);
