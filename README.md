SELECT A.first_name, A.last_name

FROM Runners AS A

INNER JOIN Registrations AS B

ON A.runner_id = B.runner_id

WHERE (B.race_name = ‘Spring 10K’ AND (B.age_group BETWEEN ‘25’ AND ‘31’));
