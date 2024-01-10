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
