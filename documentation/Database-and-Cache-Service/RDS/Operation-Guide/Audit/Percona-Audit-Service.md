# Percona Audit Service
After the log audit of Percona service is started, all operation statistics of DML and DDL will be recorded.
SQL audit will not analyze the actual parameters, and a small number of records will be lost in case of heavy SQL queries. Therefore, the incremental data may be inaccurate by such statistics way.

## Precautions
* The SQL audit will only be displayed when the instance is in high security mode.
* SQL statements executed through the console DMS tool will not be covered in the SQL audit. 

## Operation Steps
1. Login [RDS Management Console](https://rds-console.jdcloud.com/database).  
2. Select the instance that requires SQL audit query, click the target instance, enter the instance detailed page, and switch to the ***SQL Audit*** Tab page. The SQL audit query function are listed below.  
    * Execution Time: The time period of the SQL audit query can be one month earlier than the current time.
    * Database: Specified SQL statements of the database can be viewed.
    * Account: SQL statement of the specified account can be viewed.
    * Keywords: With specified keywords as the filtering condition, only SQL statements filtered out through specified keywords can be displayed.

    ![Screenshot](https://img1.jcloudcs.com/cms/0fb72d45-8e54-4ef9-a4c1-a1af3b66421020180319113956.png)

3. Click *** Query *** to see a list of SQL that meets the requirements.
