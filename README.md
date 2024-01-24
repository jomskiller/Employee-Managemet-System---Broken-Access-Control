# Employee-Managemet-System---Broken-Access-Control


Title: Broken Access Control

Affected Component:  
/employee_akpoly/Admin/delete-leave.php
/employee_akpoly/Admin/process_leave.php?id=requestid

CWE-284: Improper Access Control

CVSS 3.1 Score: 5.5

Impact: Broken access control vulnerabilities (CWE-284) pose a significant threat, potentially resulting in unauthorized access, data breaches, privilege escalation, and data manipulation. Such vulnerabilities may compromise the confidentiality of sensitive information, lead to inaccurate data, and elevate the risk of unauthorized account access. Beyond immediate security concerns, the regulatory non-compliance resulting from these issues can have legal repercussions, while the ensuing business disruption and reputation damage may incur financial and long-term consequences. To mitigate these impacts, organizations must implement robust access controls, adhere to the principle of least privilege, and regularly assess and address access control vulnerabilities through comprehensive security practices.

Proof of Concept (POC): Multiple Authenticated Broken Access control 
Only administrators are allowed to decline or approved a Leave request but we due to weak security measures implemented I was able to decline and accept a request for leave as a employee user.

To replicate the attack:
1.Login as a employee 
Visit /employee_akpoly/Employee/index.php and intercept the request using burpsuite.