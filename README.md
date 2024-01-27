# Azure Database Migration 



# Milestone 1 - Set up the Enviroment 


# Milestone 2 - Set up the Production Enviroment 
Provision a Windows VM, Install SQL Server and Server Managment Studio on the W VM in order to effectively manage and interact with the database. 

2.1 Set up a Windows Virtual Machine (VM) to serve as the cornerstone of your production environment. This VM will emulate the functions of a Windows server, replicating the operations of an on-premise system within a company.

Throughout the course of this project, the VM will act as a repository for the company's database. This setup effectively simulates a secure and dedicated data storage solution.

Ensure that you configure the appropriate network settings and firewall rules. This configuration will enable you to establish a connection to the VM using the RDP protocol.

2.2 
After provisioning the VM, the next step is to initiate a remote connect to it. Use the RDP protocol and Microsoft Remote Desktop to establish a secure connection to the VM.

This connection will provide you with direct access to the VM's operating system, facilitating efficient management and configuration.


2.3 
Install SQL Server and SQL Server Management Studio (SSMS) on the VM. These tools are essential for proficient database management within your production environment, mirroring the capabilities of a corporate database server.

2.4
Create the production database by restoring it from this backup file

. The backup file corresponds to the renowned Microsoft SQL Server database known as AdventureWorks. This database is an illustrative and comprehensive sample database that emulates a fictional manufacturing company's operations. It encompasses various tables, views, stored procedures, and data, offering a rich and diverse dataset.

By restoring the AdventureWorks database from the provided backup file, you'll replicate an authentic production database scenario.


2.5
Document your achievements in a comprehensive manner. Update the README file on the GitHub repository of this project with detailed information about the tasks accomplished in this milestone.

Provide insights into the virtual machine setup, SQL Server installation, and the creation of the production database.

# Milestone 3 

3.1 Begin by creating an Azure SQL Database, which will serve as the target for migrating your on-premise database.


Ensure that the associated SQL Server uses SQL login as the chosen authentication method. Additionally, confirm that the SQL Server has the appropriate firewall rules, specifically with your IP address added to the firewall settings.

I created the Azure SQL Database, The SQL Database server and Connected it to VSCode with SQL Login Credentials. Whilst setting up firewall exemptions for my local IP. 

3.2 
Prepared for Database migration - Install and configure Azure Data Studio on your production Windows VM. Use this tool to establish a connection to the existing on-premise database.

3.3 
Connected to Azure SQL Database - Using Azure Data Studio establish a connection to the newly created Azure SQL Database. This connection servers as the conduit for schema and data migration between the two databases.

3.4 
Shema Migration - After establishing connections to both databases, proceed to install the SQL Server Schema Compare extension within Azure Data Studio.

Leverage this extension to compare and subsequently migrate the schema from the on-premise database to the Azure SQL Database.

3.5 
Data Migration - With the successful execution of the schema migration, you are now prepared to move forward with the data migration phase. Begin by installing the Azure SQL Migration extension within Azure Data Studio.

This extension facilitates the smooth transfer of data from your on-premise database to the Azure SQL Database, ensuring a successful and seamless data migration process.


3.6 
Validate migration success - To confirm the success of the database migration process, carry out a comprehensive validation. Thoroughly inspect the data, schema, and any configurations of the migrated database, ensuring that the migration has been executed successfully and adheres to principles of data integrity.


# Milestone 4 - Data backup and Restore

4.1 
Backup the on-premise database - Begin by generating a full backup of the production database hosted on the Windows VM. This backup essentially duplicates your database, providing a safety net in the event of unforeseen issues.

Once the backup is complete, store the resultant backup file in a designated location on your computer.

4.2 
Upload the backup to blob storage- Start by configuring an Azure Blob Storage account, which will serve as a secure online repository for your database backups.

Next, upload the previously created database backup file to the Blob Storage container. This step provides an extra layer of backup protection through the presence of a redundant copy stored remotely.

4.3 
Restore Database on Development Enviroment-
Think of the development environment as an area for controlled experimentation, much like a sandbox. In software development, a sandbox is a controlled and isolated environment where applications and software can be tested, developed, and experimented with, all without impacting the production systems.

To replicate this environment, provision a new Windows VM that mirrors the development setup. Install SQL Server on this VM to mimic the necessary database infrastructure.

Subsequently, proceed to restore the database backup onto this new "sandbox" environment. This allows you to safely explore and experiment with new concepts, while your main production data remains unaffected.

4.4 
Automate Backups for Development Database- 
On your development Windows VM, utilize SSMS to establish a Management Task that automates regular backups of your development database.

Configure a weekly backup schedule to ensure consistent protection for your evolving work and simplify recovery for your development environment if needed.

# Milestone 5 - Disaster Recovery Simulation 
5.1 
Mimic Data Loss In Production Enviroment- 
Deliberately remove critical data from your production database to replicate a scenario where data integrity is compromised. You have the flexibility to choose which data to remove, but ensure that you document this simulated data loss meticulously. This documentation will serve as a blueprint for your recovery testing.

After completing the simulation, confirm its success by examining the Azure SQL Database using the connection already established in Azure Data Studio.

5.2 
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

restored to 1 hr prior 

New Database name = -restoreddatabasejeanvil

Then deleted the dataloss server in the azure portal

# Milestone 6 - Georeplication and Failover
Confirgure a Georeplication for Production Database. 

6.1 - Setup Geo Replication in Azure SQL Database 

6.2 - Test Failover and Failback 



# Milestone 7 - Microsoft Entra Directory Integration


