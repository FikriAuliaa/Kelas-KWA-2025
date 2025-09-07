# No. 4 - Database Schema
---
### Objective: Exfiltrate the entire DB schema definition via SQL Injection.
---
### Method: SQL Injection
---

### Step 1: Finding vulnerability
Identify a vulnerable parameter for SQL injection. The product search function, located at /rest/products/search?q=payload, is used for this task. The q parameter is the injection point.
<img width="1919" height="962" alt="image" src="https://github.com/user-attachments/assets/4a144335-5c6f-4822-86aa-cc19449003ac" />
<img width="1919" height="1014" alt="image" src="https://github.com/user-attachments/assets/58bce8d9-8062-49b7-bab5-e663dd076a41" />

### Step 2: Making payload
Using SQL UNION, we can inject a query to reveal the database schema. Since the product search results are displayed in a structured format with a specific number of columns, the SQL injection payload must match this column count. The payload test')) UNION SELECT 1, 2, 3, 4, 5, 6, 7, 8, sql FROM sqlite_schema-- will fulfill this requirement and successfully extract schema details from the sqlite_schema table.
<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/1d826845-dea5-486e-b0aa-4c42b5de1650" />

### Step 3: Result
<img width="1919" height="1016" alt="image" src="https://github.com/user-attachments/assets/33c8d34a-cc45-4744-a246-39b645b35c0a" />
