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

# Usage of Reimburse Application
- Run com.example.demo.ReimburseApplication as a Java Application.
Runs on port of Spring Boot - 8080

API Usage 

- 

- Run com.example.demo.EmailSenderApplication as a Java Application.
Runs on port of Spring Boot - 8081 
Run com.example.demo.EmployeeTravelPackageApplication as a Java Application.

Runs on port of Spring Boot - 8080

API usage

- http://localhost:8080/employee/get-req-by-empid/{empID}
```text
Gets All Reimbursement Requests by Employee ID{id}
```
- http://localhost:8080/employee/newrequest
```JSON
{
  "reimEmpId" : "5",
  "date" : "Sept. 6, 2021",
  "status" : "Approved",
  "amount" : "1500"
}
```
- http://localhost:8080/manager/get-req-by-empid/{empID}
```text
Gets All Reimbursement Requests by Employee ID{id}.
```
- http://localhost:8080/manager/status-update/{reqid}
```text
Patch Request that takes Reimbursement Request ID{reqid} in URL and takes a JSON body of "Pending", "Denied", or "Approved"; there is a check to make sure only these words are inputted. A manager cannot change a Denied Request.
Using the Reimbursement Request ID, this Controller grabs the Employee's email, the Reimbursement Amount, and the Reimbursement Status; they will be sent to the EmailSenderApplication to be used in e-Mail sent. 
```
- http://localhost:8080/reimman/get-req-by-empid/{empID}
```text
Gets All Reimbursement Requests by Employee ID{id}.
```
- http://localhost:8080/reimman/status-update/{reqid}
```text
Patch Request that takes Reimbursement Request ID{reqid} in URL and takes a JSON body of "Pending", "Denied", or "Approved"; there is a check to make sure only these words are inputted. 
Using the Reimbursement Request ID, this Controller grabs the Employee's email, the Reimbursement Amount, and the Reimbursement Status; they will be sent to the EmailSenderApplication to be used in e-Mail sent. 
```
