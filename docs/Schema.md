# Details about the Schema
-  pk stands for public key
## Employer table ##
+ __id__ is the primary key 
+ __pk__ is the global secondary index (Employer unique identifer)
## Employee table
+ __id__ is the primary key 
+  __pk__ is the global secondary index (Employee unique identifer) 
## Referral
+ __*employer_id and employee_id*__  are the primary keys
+ __*employer_id and employee_id*__ are the foreign keys from the Employer and Employee table
