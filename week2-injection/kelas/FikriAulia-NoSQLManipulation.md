# No. 7 - NoSQL Manipulation
---
### Objective: Update multiple product reviews at the same time.
---
### Method: noSQL Injection
---

### Step 1: Try update request and capture the payload
Identify a vulnerable parameter for SQL injection. The product search function, located at /rest/products/search?q=payload, is used for this task. The q parameter is the injection point.
<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/eb250c00-403b-42a3-a4b4-ff17a4d3ba8f" />
<img width="1919" height="1021" alt="image" src="https://github.com/user-attachments/assets/4cea030c-6dc4-4443-b25f-282fca097e84" />
<img width="1919" height="1016" alt="image" src="https://github.com/user-attachments/assets/766f3d97-923c-4189-b771-903226484f67" />

### Step 2: Manipulate the payload
`{"$ne": null}`

This is a NoSQL Injection payload. It's used to bypass authentication in a MongoDB database by forcing the query to return all records where the password is not null, which is always true for any valid account.

### Step 3: Result
The request updated all of the data not only the specified one
<img width="1919" height="1007" alt="image" src="https://github.com/user-attachments/assets/afa9e441-112b-4e0e-833a-4d71ff946c29" />
