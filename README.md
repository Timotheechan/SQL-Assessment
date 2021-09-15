# SQL-Assessment

What are the Top 25 schools (.edu domains)?

SELECT email_domain,
COUNT(user_id) AS Student_emails
FROM users
GROUP BY email_domain
ORDER BY Student_emails DESC
LIMIT 25;




How many .edu learners are located in New York?

SELECT COUNT (user_id)
FROM users
WHERE email_domain LIKE '%.edu%'
AND city = "New York";




The mobile_app column contains either mobile-user or NULL. How many of these Codecademy learners are using the mobile app?

SELECT COUNT (user_id)
FROM users
WHERE mobile_app = "mobile-user";




Query for the sign up counts for each hour.

SELECT sign_up_at,
   strftime('%H', sign_up_at)
FROM users
ORDER BY strftime('%H', sign_up_at) DESC;




Do different schools (.edu domains) prefer different courses?

SELECT
  users.email_domain,progress.*
FROM users
JOIN progress 
ON users.user_id=progress.user_id
ORDER BY users.email_domain;




What courses are the New Yorkers students taking?

SELECT
  users.email_domain,users.city,progress.*
FROM users
JOIN progress 
ON users.user_id=progress.user_id
WHERE city = "New York"
ORDER BY users.email_domain;





What courses are the Chicago students taking?

SELECT
  users.email_domain,users.city,progress.*
FROM users
JOIN progress 
ON users.user_id=progress.user_id
WHERE city = "Chicago"
ORDER BY users.email_domain;




What did you like about this project?
Its codecademy! able to get hints

What did you struggle with in this project?
Its codecademy! Instructions arent really clear and in the instructions they miss out stated a "city" field.
They only gave us:
users table:

user_id
email_domain
country
postal
mobile_app
sign_up_at

What would make your experience with this assessment better?
to be able to use the SQL workbench platform, its more relevant and relatable to our project later on
