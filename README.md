# Employee-Managemet-System---Broken-Access-Control

Affected Web app: https://www.sourcecodester.com/php/16999/employee-management-system.html

Title: Broken Access Control

Affected Component:  
/employee_akpoly/Admin/delete-leave.php
/employee_akpoly/Admin/process_leave.php?id=requestid

CWE-284: Improper Access Control

CVSS 3.1 Score: 5.5 (self - rated with the help of online CVSS calculator)

Impact: Broken access control vulnerabilities (CWE-284) pose a significant threat, potentially resulting in unauthorized access, data breaches, privilege escalation, and data manipulation. Such vulnerabilities may compromise the confidentiality of sensitive information, lead to inaccurate data, and elevate the risk of unauthorized account access. Beyond immediate security concerns, the regulatory non-compliance resulting from these issues can have legal repercussions, while the ensuing business disruption and reputation damage may incur financial and long-term consequences. To mitigate these impacts, organizations must implement robust access controls, adhere to the principle of least privilege, and regularly assess and address access control vulnerabilities through comprehensive security practices.

Proof of Concept (POC): Multiple Authenticated Broken Access control 
Only administrators are allowed to decline or approved a Leave request but we due to weak security measures implemented I was able to decline and accept a request for leave as a employee user.

To replicate the attack:
1.Login as a employee 
2.Visit /employee_akpoly/Employee/index.php and intercept the request using burpsuite.

![image1](https://github.com/jomskiller/Employee-Managemet-System---Broken-Access-Control/blob/main/image1.png)

3.Change the target url of the GET method to /employee_akpoly/Admin/delete-leave.php?id=requestid you want to decline if you want to accept use /employee_akpoly/Admin/process_leave.php?id=requestid 
Note: on id parameter input the requestid of the request you want to approve or decline.

![image2](https://github.com/jomskiller/Employee-Managemet-System---Broken-Access-Control/blob/main/image2.png)
![image3](https://github.com/jomskiller/Employee-Managemet-System---Broken-Access-Control/blob/main/image3.png)

Remediation: To remediate broken access control vulnerabilities (CWE-284), organizations should prioritize implementing Role-Based Access Control (RBAC) and enforcing the principle of least privilege. RBAC ensures that users are assigned permissions based on their roles, reducing the risk of unauthorized access. Adhering to the principle of least privilege involves granting users only the minimum necessary permissions for their specific tasks, minimizing potential security risks. Additionally, the use of Access Control Lists (ACLs) allows for granular control over resource access. Regular access reviews should be conducted to identify and revoke unnecessary or outdated privileges. Security awareness training for employees further reinforces the importance of access control and the handling of sensitive information. Robust monitoring and auditing mechanisms aid in detecting unauthorized access attempts, while the implementation of secure session management practices adds an extra layer of protection. These measures collectively contribute to a more secure environment, reducing the likelihood of unauthorized access and potential data breaches.
