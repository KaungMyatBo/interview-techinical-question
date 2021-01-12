# Requirements
Assume you are creating a Clinic Application. You need to create two JAVA modules.
## Patient Visit Module
This must be runnable working web application. You need to provide end to end (RESTful API, service and dao) implementation for CURD operations for business domain entities below:
* Patient
* Physician
* Visit

Assume identifier (ID) for these domain entities will be defined by users during filling the form.
When the entity is created, you need to implement 2 requirements below:
* Data duplication must be checked before persisting to storage medium. If there is any data with same ID, duplicate exception must be thrown back to caller. 
* If data is created during the holiday, holiday exception must be thrown back to caller.

When the entity is updated or delete
* If data is modified during the holiday, holiday exception must be thrown back to caller. 

You may have a static class to provide static login user id value.
This module must be independently runnable module without Billing Module
## Billing Module
After a visit entity is created, a billing entity related to that visit shall be created only if billing module is part of the deployment. Which mean, some clients may not want billing module as a part of the whole application.
## Storage Medium Requirement
MySQL DB shall be used as a basic DB for this application. But based on the client’s needs, the application must support not only RDBMS but also any NoSQL DB which are not supported by Hibernate. When new DB is introduced, your implemented project structure must be flexible enough and implemented codes in API and Service classes must have minimum impact or no impact (better). Main point is, because of storage medium changes, logic codes in Service and API classes should not be effected.
## Technical Requirement
* Backend: Spring Boot
* MySQL
## Business Domain Entity
### Patient
* ID
* Name
* Age
* Gender
* Created Datetime
* Modifed Datetime
* Created By
### Physician
* ID
* Name
* Created Datetime
* Modified Datetime
* Created By
* Modified By
### Visit
* ID
* Visit Datetime
* Physician ID
* Reason
* Created Datetime
* Modified Datetime
* Created By
* Modified By
### Holiday
* Name
* Holiday Date
* Created Datetime
* Modified Datetime
* Created By
* Modified By
### Billing
* ID
* Patient ID
* Physician ID
* Billed Datetime
