# Azure Database Migration 

See Azure Project PDF in Repo for UML Diagram of Build Architecture. 

In this project, I architected and implemented a cloud-based database system on Microsoft Azure, showcasing my hands-on expertise in cloud engineering.

I began by establishing a production environment database. Subsequently, I migrated the database to Azure SQL Database, focusing on crucial aspects like data backup, restoration, and automated scheduling. These efforts strengthened my data management approach.

A pivotal phase of the project involved simulating a disaster recovery scenario with potential data loss. Furthermore, I explored the complexities of geo-replication and failover configuration to ensure data availability even under challenging conditions.

To enhance security, I employed Microsoft Entra ID integration to define access roles like read only, adding an extra layer of control and protection.


I approached and completed this project with different milestones and maintaining the practice of continually updating my GitHub README documentation with my recent tasks. 


# Milestone 1 - Set up the Enviroment 

First I Set up an Azure account 


# Milestone 2 - Set up the Production Enviroment 

I provisioned a Windows VM and installed SQL Server and Server Management Studio on the VM to effectively manage and interact with the database.

2.1 I set up a Windows Virtual Machine (VM) to serve as the cornerstone of our production environment, emulating the functions of a Windows server.

Throughout the course of this project, the VM acted as a repository for our company's database, providing a secure and dedicated data storage solution.

I configured the appropriate network settings and firewall rules to establish a connection to the VM using the RDP protocol.

2.2 After provisioning the VM, I initiated a remote connection to it using the RDP protocol and Microsoft Remote Desktop, facilitating efficient management and configuration.

2.3 I installed SQL Server and SQL Server Management Studio (SSMS) on the VM, essential tools for proficient database management within our production environment, mimicking the capabilities of a corporate database server.

2.4 I created the production database by restoring it from a backup file, corresponding to the renowned Microsoft SQL Server database known as AdventureWorks.

By restoring the AdventureWorks database from the provided backup file, I replicated an authentic production database scenario.

2.5 I documented my achievements comprehensively, updating the README file on the GitHub repository of this project with detailed information about the tasks accomplished in this milestone.Provision a Windows VM, Install SQL Server and Server Managment Studio on the W VM in order to effectively manage and interact with the database. 

# Milestone 3 

3.1 I began by creating an Azure SQL Database, serving as the target for migrating our on-premise database.

I ensured that the associated SQL Server used SQL login as the chosen authentication method and configured the appropriate firewall rules.

I created the Azure SQL Database, the SQL Database server, and connected it to VSCode with SQL Login Credentials, setting up firewall exemptions for my local IP.

3.2 I prepared for database migration by installing and configuring Azure Data Studio on our production Windows VM, using this tool to establish a connection to the existing on-premise database.

3.3 Using Azure Data Studio, I connected to the newly created Azure SQL Database, establishing a conduit for schema and data migration between the two databases.

3.4 I installed the SQL Server Schema Compare extension within Azure Data Studio to compare and subsequently migrate the schema from the on-premise database to the Azure SQL Database.

3.5 With the successful execution of the schema migration, I proceeded to install the Azure SQL Migration extension within Azure Data Studio to facilitate the smooth transfer of data from our on-premise database to the Azure SQL Database.

3.6 I validated the migration success by thoroughly inspecting the data, schema, and configurations of the migrated database, ensuring a successful and seamless data migration process.

# Milestone 4 - Data backup and Restore

4.1 I backed up the on-premise database by generating a full backup of the production database hosted on the Windows VM, storing the resultant backup file in a designated location on my computer.

4.2 I uploaded the backup to blob storage by configuring an Azure Blob Storage account, serving as a secure online repository for our database backups, and uploading the previously created database backup file to the Blob Storage container.

4.3 I restored the database on the development environment, provisioning a new Windows VM, installing SQL Server on this VM, and restoring the database backup onto this new "sandbox" environment.

4.4 On the development Windows VM, I utilized SSMS to establish a Management Task that automated regular backups of our development database, configuring a weekly backup schedule.

# Milestone 5 - Disaster Recovery Simulation 
5.1 I mimicked data loss in the production environment by deliberately removing critical data from our production database, meticulously documenting this simulated data loss and confirming its success by examining the Azure SQL Database using the connection already established in Azure Data Studio.

5.2 I restored the database from the Azure SQL Database backup, conducting tests and verifying the restoration process to ensure data integrity.

Procedure as Follows:
Restore Database from Azure SQL Database Backup- 

Deleted first 100 Rows for: 

Person.Address Table 

Corrputed 100 Rows: Person.Password Table 

DELETE TOP (100)
FROM Person.Address;

UPDATE TOP (100) Person.Password
SET PasswordHash = 0 ‘

Checked Dataloss:

Verified by inspecting tables 

Databasejeanvil production vm 

Restored through azure portal 

I then restored tbe production database to a period pre-data loss/disaster. In this case 1 hr prior.

New Database name = -restoreddatabasejeanvil

Then deleted the dataloss server in the azure portal

# Milestone 6 - Georeplication and Failover
Confirgure a Georeplication for Production Database. 

6.1 I set up geo-replication for our production Azure SQL Database, creating a synchronized replica of our primary database in a separate SQL server located in a different geographical region.

6.2 I tested failover and failback procedures, simulating real-world challenges by orchestrating a planned failover to the secondary region and evaluating the availability and data consistency of the failover database.

# Milestone 7 - Microsoft Entra Directory Integration

7.1 I configured Microsoft Entra ID authentication for the SQL Server hosting our Azure SQL production database, integrating Microsoft Entra ID as a trusted identity provider and establishing an Microsoft Entra admin with authority over user management and access control.

7.2 I created a database reader user, generating a new user account in Microsoft Entra ID and assigning the db_datareader role to the user for read-only privileges, ensuring correct role assignment for user permissions.





