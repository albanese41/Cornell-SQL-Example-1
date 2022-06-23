# Cornell-SQl-Examples

Here are several of the SQl Queries I created completing the Data Science SQL and Tableau Certificate through Cornell University.

SELECT A.first_name, A.last_name, B.race_name, C.race_position
FROM runners AS A
INNER JOIN registrations AS B
ON A.runner_id = B.runner_id
INNER JOIN results AS C
ON B.registration_id = C.registration_id
WHERE C.race_position = (SELECT MIN(race_position)
FROM registrations
INNER JOIN results
ON registrations.registration_id = results.registration_id
WHERE registrations.race_name = B.race_name);
