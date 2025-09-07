# No. 1 - Login Admin
---
### Objective: Log in with the administrator's user account.
---
### Method: SQL Injection
---

### Step 1: Use a simple SQL injection payload

The simple payload `' OR 1=1--` was used to bypass the login form. This works by making the database query evaluate to true, regardless of the password entered.

#### Before Injection (Normal Login Query)
The typical SQL query for a login form looks like this:
```sql
SELECT * FROM users WHERE email = 'YOUR_EMAIL_HERE' AND password = 'YOUR_PASSWORD_HERE';
```

#### After Injection (With Payload)
By entering ' OR 1=1-- into the email field and any text into the password field, the query becomes:
```sql
SELECT * FROM users WHERE email = '' OR 1=1--' AND password = 'ANY_PASSWORD';
```
The ' closes the email string. The OR 1=1 adds a condition that is always true. The -- at the end acts as a comment, telling the database to ignore the rest of the original query (including the password check). Because 1=1 is always true, the database returns the first user in the table, which is typically the administrator.

### Step 2: Verification of Success
The login was successful, confirming that the SQL injection payload worked as intended, bypassing the need for a valid password.

<img width="1918" height="971" alt="image" src="https://github.com/user-attachments/assets/2eb5ef33-c4b1-44c7-9f8c-d193c7fb04a1" />
<img width="1919" height="461" alt="image" src="https://github.com/user-attachments/assets/d8a0d468-37fa-416b-a01b-8dbe68850bf3" />

