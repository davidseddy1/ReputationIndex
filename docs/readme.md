# Reputation Index Score Design

This page displays high level design content for the reputation index.

!["RUI Sequence Diagram"](./output/RUI_Sequence_Diagram.svg)

The following diagram depicts the data model for the reputation index.
There are 3 tables used for storing referral data, loan applicant data, and employee data.

## Employer table

![Employer Table](./output/employer_table.svg)

+ __id__ is the primary key (Employer unique identifer)

## Employee table
 ![Employee Table](./output/employee_table.svg)

+ __id__ is the primary key (Employee unique identifier)

## Referral

+ __id__ is the primary key
+ __*employer_id and employee_id*__ are the foreign keys from the Employer and Employee table

!["Database Data Model"](./output/DB_tables.svg)