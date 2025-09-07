# No. 2 - Login Jim
---
### Objective: Log in with Jim's user account.
---
### Method: SQL Injection
---

### Step 1: Search for Jim's email in the page
<img width="1919" height="968" alt="Screenshot 2025-09-04 150835" src="https://github.com/user-attachments/assets/eaf0c87a-5d98-4f74-a5cc-539f785e00b0" />

### Step 2: Use a simple SQL injection payload
The simple payload `' OR '1'='1' --` was used to bypass the login form. This works by making the database query evaluate to true, regardless of the password entered.

### Step 3: Verification of Success
The login was successful, confirming that the SQL injection payload worked as intended, bypassing the need for a valid password.
<img width="1919" height="970" alt="Screenshot 2025-09-04 151418" src="https://github.com/user-attachments/assets/d4bcca33-de6c-47b2-8ac0-0df6804d2727" />
