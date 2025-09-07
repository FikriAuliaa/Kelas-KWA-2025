# No. 8 - User Credentials
---
### Objective: Retrieve a list of all user credentials via SQL Injection.
---
### Method: SQL Injection
---

### Step 1: Finding vulnerability
Identify a vulnerable parameter for SQL injection. The product search function, located at /rest/products/search?q=payload, is used for this task. The q parameter is the injection point.
<img width="1919" height="1018" alt="image" src="https://github.com/user-attachments/assets/bbfaf805-f079-4969-ba8e-5a8f07407ac2" />
<img width="1917" height="260" alt="image" src="https://github.com/user-attachments/assets/f341ac76-9dc2-4116-a273-9f447b328aaf" />

### Step 2: Making payload
`' OR 1=1 /**/` is an SQL Injection payload used to bypass authentication. It works by making a database query always true, regardless of the password. The ' closes the initial string, the OR 1=1 adds a condition that's always met, and the /**/ comments out the rest of the original query, effectively tricking the database into logging you in without a valid password.


### Step 4: Result
We get all of the database including user credentials
<img width="1919" height="1027" alt="image" src="https://github.com/user-attachments/assets/d9c7df6b-2c79-4de3-b3fa-82bc85a0d6a0" />


