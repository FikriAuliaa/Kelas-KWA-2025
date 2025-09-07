# No. 1 - Login Admin
---
### Objective: Log in with the administrator's user account.
---
### Method: SQL Injection
---

### Step 1: Use a simple SQL injection payload
The simple payload `' OR true--` was used to bypass the login form. This works by making the database query evaluate to true, regardless of the password entered.

### Step 2: Verification of Success
The login was successful, confirming that the SQL injection payload worked as intended, bypassing the need for a valid password.
<img width="1918" height="971" alt="image" src="https://github.com/user-attachments/assets/2eb5ef33-c4b1-44c7-9f8c-d193c7fb04a1" />
<img width="1919" height="461" alt="image" src="https://github.com/user-attachments/assets/d8a0d468-37fa-416b-a01b-8dbe68850bf3" />

