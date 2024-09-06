# Introduction & Foundational Skills (Focus on Project Relevance)

Welcome to Week 1! This week, we’ll be diving into the exciting world of SQL and databases! We’ll explore what SQL is used for, how it benefits web applications, and the building blocks of databases: tables, columns, and data types. But most importantly, we’ll get hands-on experience by creating a basic database structure for our upcoming project!

<br/>

## Learning Objectives:
- Understand the purpose and applications of SQL, particularly for web applications.
- Identify the fundamental components of a database: tables, columns, and data types.
- Design a basic database schema for our project.

<br/>
  
## Instructions
This assignment is designed to be completed in approximately 2 hours.

### What you’ll need:
- Access to a computer with internet access
- A code editor (e.g., Visual Studio Code)
- Drawing software (e.g., Draw.io, Visual Paradigm) for the bonus question.

<br/>
  
## Submission
- Clone the project on your local computer
- Create a file named ```answers.sql```
- Run the queries on MySQL workbench and once they are successfull copy and paste on the ```answers.sql``` file on VS code
- Make sure you clearly comment your answers. Example:
```sql
-- question 1.1
CREATE TABLE table_0 (
    column1 datatype,
    column2 datatype
);

-- question 1.2
CREATE TABLE table_1 (
    column1 datatype,
    column2 datatype
);
```
- Once you finish the assignment, push the code to github

<br/>
  
## Part 1: Database Modelling
Using a software of choice eg. draw.io, lucid chart etc, draw a well defined Entity Relationship Diagram (ERD) of the database whose fields are outlined below. Once you are done export or download the diagram in pdf format and upload it on the repository or you can copy and paste it to the cloned repository before you push the changes

<br/><br/>
**Table Name:** patients
| FIELD | DATA TYPE | CONSTRAINTS |
|------------|--------------|-----------------|
| patient_id | INT | PRIMARY KEY, AUTO_INCREMENT |
| first_name | VARCHAR | NOT NULL|
| last_name | VARCHAR | NOT NULL |
| date_of_birth | DATE | NOT NULL |
| gender | VARCHAR | NOT NULL |
| language | VARCHAR | NOT NULL |


<br/><br/>
**Table Name:** providers
| FIELD | DATA TYPE | CONSTRAINTS |
|------------|--------------|-----------------|
| provider_id | INT | PRIMARY KEY AUTO_INCREMENT |
| first_name | VARCHAR | NOT NULL |
| last_name | VARCHAR | NOT NULL |
| provider_speciality | VARCHAR | NOT NULL |
| email_address | VARCHAR |  |
| phone_number | VARCHAR |  |
| date_joined | DATE | NOT NULL |

<br/><br/>
**Table Name:** visits
| FIELD | DATA TYPE | CONSTRAINTS |
|------------|--------------|-----------------|
| visit_id | INT | PRIMARY KEY, AUTO_INCREMENT |
| patient_id | INT | FOREIGN KEY REFERENCES patients(patient_id) |
| provider_id | INT | FOREIGN KEY REFERENCES providers(provider_id) |
| date_of_visit | DATE | NOT NULL |
| date_scheduled | DATE | NOT NULL |
| visit_department_id | INT | NOT |
| visit_type | VARCHAR | NOT NULL |
| blood_pressure_systollic | INT | |
| blood_pressure_diastollic | DECIMAL | |
| pulse | DECIMAL |  |
| visit_status | VARCHAR | NOT NULL|

<br/><br/>
**Table Name:** ed_visits
| FIELD | DATA TYPE | CONSTRAINTS |
|------------|--------------|-----------------|
| ed_visit_id | INT | PRIMARY KEY, AUTO_INCREMENT |
| visit_id | INT | FOREIGN KEY REFERENCES visits(visit_id) |
| patient_id | INT | FOREIGN KEY REFERENCES patients(patient_id) |
| acuity | INT | NOT NULL |
| reason_for_visit | VARCHAR | NOT NULL |
| disposition | VARCHAR | NOT NULL |

<br/><br/>
**Table Name:** admissions
| FIELD | DATA TYPE | CONSTRAINTS |
|------------|--------------|-----------------|
| admission_id | INT | PRIMARY KEY, AUTO_INCREMENT |
| patient_id | INT | FOREIGN KEY REFERENCE patients(patients_id) |
| admission_date | DATE | NOT NULL |
| discharge_date | DATE | NOT NULL |
| discharge_disposition | VARCHAR | NOT NULL |
| service | VARCHAR | NOT NULL |
| primary_diagnosis | VARCHAR | NOT NULL |


<br/><br/>
**Table Name:** discharges
| FIELD | DATA TYPE | CONSTRAINTS |
|------------|--------------|-----------------|
| discharge_id | INT | PRIMARY_KEY, AUTO_INCREMENT |
| admission_id | INT | FOREIGN KEY REFERENCES admissions(admission_id) |
| patient_id | INT | FOREIGN KEY REFERENCES patients(patients_id) |
| discharge_date | DATE | NOT NULL|
| discharge_disposition | VARCHAR | NOT NULL |

<br/><br/>
## Part 2: Creating a database
Now that you have already created a model of your database, it is time to bring it start building on it. Create database named ```hospital_db```.

<br/><br/>
## Part 3: Creating Tables
After creating your your database the next step is creating your tables, but before we start making any changes to the database, we need to make sure it is selected. Select the database using the ```USE``` keyword.<br/>
After selecting the databse proceed to create the tables using the information provided in the tables above. For Example
```sql
CREATE TABLE patients(
    patient_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    date_of_birth DATE NOT NULL,
    gender VARCHAR(10),
    language VARCHAR(20) NOT NULL
);
```

<br/><br/>
## NOTE: You should not fork the repository
Remember: There might be multiple ways to design your database schema. The goal is to understand the concepts and create a logical structure to store your project data.


