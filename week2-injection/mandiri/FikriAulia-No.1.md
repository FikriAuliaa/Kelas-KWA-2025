# No.1 Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

### Step 1: Use Burp Suite to intercept and modify the request that sets the product category filter.
<img width="1919" height="960" alt="image" src="https://github.com/user-attachments/assets/e095ea20-453a-44cb-a594-a01a29435e5f" />
<img width="1919" height="111" alt="image" src="https://github.com/user-attachments/assets/783b2de5-db1e-4abf-9fac-d9b02506aa81" />

### Step 2: Modify the category parameter
giving it the value `'+OR+1=1--` Submit the request, and verify that the response now contains one or more unreleased products.
<img width="1919" height="1010" alt="image" src="https://github.com/user-attachments/assets/42a1e276-69ac-4026-bbe9-6211b2915374" />
<img width="1917" height="905" alt="image" src="https://github.com/user-attachments/assets/1d857e49-c0c8-4376-8369-66ad1071f920" />
