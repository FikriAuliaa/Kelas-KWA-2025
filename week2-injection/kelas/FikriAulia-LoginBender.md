# No. 3 - Login Bender
---
### Objective: Log in with Bender's user account.
---
### Method: SQL Injection
---

### Step 1: Search for Bender's email in the page
<img width="1919" height="965" alt="image" src="https://github.com/user-attachments/assets/63583369-dbc8-44d0-ad41-2248258d70c5" />

### Step 2: Use a simple SQL injection payload
The simple payload `'--` was used to bypass the login form. This works by making the database query evaluate to true, regardless of the password entered.

### Step 3: Verification of Success
The login was successful, confirming that the SQL injection payload worked as intended, bypassing the need for a valid password.
<img width="1919" height="968" alt="Screenshot 2025-09-04 152031" src="https://github.com/user-attachments/assets/604c5cbd-3701-422c-905d-e68a3c8b0a8e" />
<img width="1917" height="651" alt="image" src="https://github.com/user-attachments/assets/d79a18fd-6545-46d8-938e-acfd889567fa" />

