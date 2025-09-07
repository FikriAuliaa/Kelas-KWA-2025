# No. 5 - Christmas Special
---
### Objective: Order the Christmas special offer of 2014.
---
### Method: SQL Injection
---

### Step 1: Finding vulnerability
Identify a vulnerable parameter for SQL injection. The product search function, located at /rest/products/search?q=payload, is used for this task. The q parameter is the injection point.

### Step 2: Making payload
the payload test')) UNION SELECT * FROM PRODUCTS WHERE deletedAt IS NOT NULL-- is an SQL injection designed to find and reveal hidden or discontinued products.
Instead of a login bypass, it forces the database to show items that have been "soft-deleted" by looking for entries where the deletedAt column is not empty.
<img width="1918" height="1020" alt="image" src="https://github.com/user-attachments/assets/d10b4abf-7fd8-4146-a4a3-e74352702877" />
<img width="1919" height="1026" alt="Screenshot 2025-09-04 210824" src="https://github.com/user-attachments/assets/bc7ab96f-b4f2-42d6-921c-933c14991089" />
Now we know that the productId for the items is "10"

### Step 3: Manipulating the Item
Add a product to cart and capture the payload
<img width="1918" height="1014" alt="image" src="https://github.com/user-attachments/assets/ffb42cd2-30cc-49b1-a2b8-2ab1db38c51d" />

Change the productID to "10"
<img width="1919" height="1015" alt="image" src="https://github.com/user-attachments/assets/8bf1e155-35e7-4d97-9fb6-4356c4b2bcc0" />

### Step 4: Result
We get the "hidden" item
<img width="1919" height="1021" alt="image" src="https://github.com/user-attachments/assets/88989bf7-6c8e-45a7-9d8c-9c87d09221e3" />
