# SQL-Injection



<img width="1024" height="1000" alt="Image" src="https://github.com/user-attachments/assets/89b0a59e-1dbd-4814-af7a-db0939e48239" />

**SQL Injection (SQLi) is a web security vulnerability that allows attackers to interfere with the queries an application makes to its database. It's one of the most common and dangerous web application vulnerabilities.**



🎯 Objective

To practically exploit SQL Injection vulnerabilities using SQLMap and manual techniques in a controlled lab environment, and understand the real-world impact of insecure database handling.

🛠 Tools Used

Primary: SQLMap

Alternative: Manual SQL Injection

Lab: DVWA / OWASP Juice Shop

📚 Skills Gained

SQL Injection exploitation

Automated database enumeration

Secure database design understanding

Vulnerability documentation




🧪 Mini Guide (Step-by-Step Mapping)


**1️⃣ Identify Injectable Parameters**

Test URL and POST parameters

Look for SQL errors or abnormal responses

Confirm injection point

📄 exploitation/identifying-injection.md


**2️⃣ Run SQLMap**

<img width="1500" heigth="200" src="https://github.com/user-attachments/assets/cd882bf2-cddf-4945-b839-cbcebba95779"/>

Basic command example:

    sqlmap -u "http://target/vuln.php?id=1" --batch


📄 exploitation/sqlmap-usage.md

**3️⃣ Extract Database Names**

      sqlmap -u "URL" --dbs


📄 exploitation/database-enumeration.md

**4️⃣ Extract Tables**

      sqlmap -u "URL" -D database_name --tables


📄 exploitation/table-enumeration.md

**5️⃣ Extract User Data**

        sqlmap -u "URL" -D database_name -T users --dump



<img width="1024" height="1000" alt="Image" src="https://github.com/user-attachments/assets/ffa468d2-aeda-437f-aefd-4d4939795e39"/>

📄 exploitation/data-extraction.md

**6️⃣ Analyze Impact**

Credential exposure

Sensitive data leakage

Full database compromise

Business risk

📄 impact-analysis/security-impact.md

**7️⃣ Document Attack Flow**

Attack chain:

    Input field → Injection point → SQLMap → Database access → Data extraction


📄 reports/sql-injection-attack-report.md

**8️⃣ Suggest Fixes**

Prepared statements

Parameterized queries

Input validation

Least privilege database users

WAF usage

📄 mitigation/sql-injection-prevention.md
