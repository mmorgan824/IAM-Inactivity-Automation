1. Windows Server 2022 Environment Configuration


<img width="1023" height="836" alt="WS22 Installation   Config" src="https://github.com/user-attachments/assets/8234ee75-57dc-4da0-96d6-0ee42f72c9c7" />



To simulate an enterprise environment, I deployed and configured a Windows Server 2022 instance within a virtualized sandbox. 
This phase involved installing and promoting Active Directory Domain Services (AD DS) and configuring the Morgantestsrv.local domain. 
As a Technical Analyst, establishing this infrastructure was critical for testing Identity and Access Management (IAM) policies in a controlled, risk-free environment that mirrors production-level directory services.



2. Automated Identity Provisioning (User Creation)

<img width="1024" height="769" alt="Automation Script of Users" src="https://github.com/user-attachments/assets/aed75405-b2bd-4488-86ec-af0f07011837" />

<img width="1015" height="766" alt="Created Users" src="https://github.com/user-attachments/assets/51945bf3-3fbc-4bbd-a114-7006bb37837b" />


I developed and executed a PowerShell automation script to perform bulk user provisioning within a dedicated TestLabUsers Organizational Unit (OU). To optimize the development lifecycle, I utilized AI-driven code generation and debugging tools to architect the PowerShell automation scripts used in this lab.
By utilizing loops and the New-ADUser cmdlet, I standardized the creation of 25 test identities with consistent naming conventions and specific security attributes. 
This project demonstrates my ability to replace manual, error-prone tasks with scalable automation, ensuring data integrity across the directory.


3. Security Audit: Inactive User Detection

<img width="1021" height="769" alt="Script for Inactive Users" src="https://github.com/user-attachments/assets/a11b8384-3aba-49e7-95ee-7d92d78722de" />


This phase focused on mitigating the risk of 'Ghost Accounts' through a custom-developed audit script. 
The automation utilizes logic to filter the directory for users whose LastLogonDate exceeds a 90-day threshold or lacks activity entirely. 
By generating a CSV-based audit trail, I provided a mechanism for stakeholder review, ensuring that security decisions are supported by documented system metadata and align with the principle of least privilege.


4. IAM Remediation and Status Verification

<img width="1023" height="766" alt="User Account Status Output" src="https://github.com/user-attachments/assets/44439a14-4508-4afd-b67a-720e172ad091" />


The final stage of the lifecycle involved executing a remediation script to programmatically disable identified stale accounts. 
I moved from the data validation phase—where I audited the Morgantestsrv.local domain—to the action phase by piping the identified user objects directly into the Disable-ADAccount cmdlet. 
Following execution, I performed a verification audit using Active Directory Users and Computers (ADUC) to confirm that the account status changes were successfully committed to the database, identified by the visual 'disabled' markers on the user icons. 
This 'closed-loop' process highlights a proactive approach to maintaining a hardened security posture and enforcing the principle of least privilege within an organization's identity infrastructure.
