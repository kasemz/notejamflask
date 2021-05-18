# notejamflask



**Notejam deployed on  Azure platform**


Notejam Notejam is a Python/Flask monolith application. The document describes a proposed approach to migrate monolithic application to containers on Azure with CI/CD.

Architecture
This application in its originaly is built as a monolith having a stateless webserver and SQLite  both are running on the same VM or machine. 

**To Improve scalability, security and devlopment**

1- the database has been decoupled and replaced by an Azure SQL Database.
2- the application is packed to Docker image and sent Azure Container register to be deployed to Azure as Webapp container based more over how to deploy can be found on (https://docs.microsoft.com/en-us/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops&tabs=java)
3- Azure Kubernetes is also implemented to improve scalability
4- Monitoring is garanted by sending the logs to log Analytics workspace.
5- It is also possible to store connections strings and key certificates in an **Azure Key Vault**.
6- **Implementing WAF** ( Web application firewall) which acts as Load balancer and firewall, might improve security.
**Benefits**
This section describes the core benefits that WAF on Application Gateway provides.

**Protection**
Protect your web applications from web vulnerabilities and attacks without modification to back-end code.

Protect multiple web applications at the same time. An instance of Application Gateway can host up to 40 websites that are protected by a web application firewall.

Create custom WAF policies for different sites behind the same WAF

Protect your web applications from malicious bots with the IP Reputation ruleset (preview)

**Monitoring**
Monitor attacks against your web applications by using a real-time WAF log. The log is integrated with Azure Monitor to track WAF alerts and easily monitor trends.

The Application Gateway WAF is integrated with Azure Security Center. Security Center provides a central view of the security state of all your Azure resources.

**Customization**
Customize WAF rules and rule groups to suit your application requirements and eliminate false positives.

Associate a WAF Policy for each site behind your WAF to allow for site-specific configuration

Create custom rules to suit the needs of your application

**Features**
SQL-injection protection.
Cross-site scripting protection.
Protection against other common web attacks, such as command injection, HTTP request smuggling, HTTP response splitting,  and remote file inclusion.
Protection against HTTP protocol violations.
Protection against HTTP protocol anomalies, such as missing host user-agent and accept headers.
Protection against crawlers and scanners.
Detection of common application misconfigurations (for example, Apache and IIS).
Configurable request size limits with lower and upper bounds.
Exclusion lists let you omit certain request attributes from a WAF evaluation. A common example is Active Directory-inserted tokens that are used for authentication or password fields.
Create custom rules to suit the specific needs of your applications.
Geo-filter traffic to allow or block certain countries/regions from gaining access to your applications. (preview)
Protect your applications from bots with the bot mitigation ruleset. (preview)
Inspect JSON and XML in the request body


**Suggusted new architecture**
![alt text](https://github.com/kasemz/notejamflask/blob/image/notejam.jpg)

**Deploy**


[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fkasemz%2Fnotejamflask%2FARM%2Ftemplate.json)

