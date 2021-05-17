# notejamflask



**Notejam deployed on  Azure platform**


Notejam Notejam is a Python/Flask monolith application. The document describes a proposed approach to migrate monolithic application to containers on Azure with CI/CD.

Architecture
This application in its originaly is built as a monolith having a stateless webserver and SQLite  both are running on the same VM or machine. 

**To Improve scalability, security and devlopment**

1- the database has been decoupled and replaced by an Azure SQL Database.
2- the application is packed to Docker image and sent Azure Container register to be deployed to Azure as Webapp container based more over how to deploy can be found on (https://docs.microsoft.com/en-us/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops&tabs=java)
3- Azure Kubernetes is alos implemented to improve scalability
4- Monitoring is garanted by sending the logs to log Analytics workspace.
5- It is also possible to store connections strings and key certificates in an Azure Key Vault.
6- Implementing WAF ( Web application firewall) which acts as Load balancer and firewall, might improve security.


**Suggusted new architecture**
![alt text](https://github.com/kasemz/notejamflask/blob/image/notejam.jpg)

