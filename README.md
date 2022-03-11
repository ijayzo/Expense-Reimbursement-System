# Reimbursement-App
The Expense Reimbursement System will manage the process of reimbursing employees for expenses incurred while on company time. All employees in the company can login and submit requests for reimbursement and view their past tickets and pending requests. Finance managers can log in and view all reimbursement requests and history for all employees in the company. Finance managers are authorized to approve and deny requests for expense reimbursement.

# Technologies Used
- Java 
- JUnit 
- Spring Boot 
- Spring Data 
- Spring MVC 
- Docker 
- Insomnia
- Log4J 
- Lombok 
- Maven 
- Git 
- Hibernate 
- PostgreSQL 
- GCP Cloud SQL

# Features
- Built 2 separarte web APIs using Spring Boot, and deployed and orchestrated the applications using Docker and Docker Compose.
- Created First API = A reimbursement app with role specific controllers/services. 
- Added Employee Role: can submit a reimbursement request, view all of my (employee) reimbursements.
- Added Manager Role: can view all reimbursements, approve/deny/reassign reimbursements. A manager can Approve a request or change it to Pending if the status is blank (null).
- Added Reimbursement Role: created to clear the reassign objective. Only a Reimbursement Manager has full access to updating any status.
- Created second API = Email API: Receive request to send emails to specified users. Grabs specific user emails, name, and reimbursement status API 1.
- Created Logging/Javadocs and presented using Insomnia.
- Created Service and Controller Testing using JUnit and Mockito.

# To-do list:
- Deploy into a Kubernetes cluster 
- Add Monitoring/Logs/Alerts

# Getting Started
- git clone https://github.com/ijayzo/Expense-Reimbursement-System.git
- Run com.example.demo.ReimburseApplication as a Java Application.
Runs on port of Spring Boot - 8080
- Run com.example.demo.EmailSenderApplication as a Java Application.
Runs on port of Spring Boot - 8081 

# Usage

Here, you instruct other people on how to use your project after they’ve installed it. This would also be a good place to include screenshots of your project in action.

Contributors
Here list the people who have contributed to this project. (ignore this section, if its a solo project)

License
This project uses the following license: <license_name>.
