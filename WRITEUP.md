Article CMS (FlaskWebProject)
This project is a Python web application built using Flask. The user can log in and out and create/edit articles. An article consists of a title, author, and body of text stored in an Azure SQL Server along with an image that is stored in Azure Blob Storage. The login system also implements OAuth2 with Sign in with Microsoft using the msal library, along with app logging.

Below four factors to consider web app vs. vms.

Cost
Web applications generally have lower costs compared to VMs. For instance, Azure App Services can be more cost-effective because they charge based on usage, whereas VMs incur costs even when idle.  Whereas, VMs has he more CPU, memory, and storage you allocate to your VM, the higher the cost. For example, a VM with 4 vCPUs and 16 GB of RAM will cost more than one with 2 vCPUs and 8 GB of RAM.

Scalability
Web applications can scale up or down based on demand without significant manual intervention. This flexibility can lead to cost savings, especially during periods of low usage.  Whereas, VMs can be scaled horizontally by adding more instances to distribute the workload. This is often managed through tools like Azure Virtual Machine Scale Sets, which automatically adjust the number of VMs based on demand.

Availability
Web applications are designed to be accessible 24/7 with minimal downtime. This is crucial for businesses that need to ensure their services are always available to users. By distributing VMs across different physical servers or data centers, you can achieve high availability and fault tolerance, ensuring your applications remain accessible even if some VMs fail.

Workflow
Web applications can easily integrate with other web services and tools, creating a cohesive ecosystem that streamlines workflows and eliminates the need for repetitive data entry. Whereas, VMs can be created with specific configurations to meet the needs of different applications. Tools like VMware vSphere and Azure Resource Manager templates allow for automated and consistent VM creation.

I decided to use a web application for this project because it offers seamless accessibility from any device with an internet connection. Additionally, web applications provide automatic updates and maintenance, ensuring the system is always up-to-date without manual intervention. Lastly, they integrate easily with other web services, streamlining workflows and enhancing productivity.

How will the app change per your decision, such as the application requirement or more control over the infrastructure?

Opting for App Service simplifies deployment and management with built-in tools and services. It automatically scales your application based on demand, reducing the need for manual intervention and minimizing operational overhead. This ease of use allows you to focus more on application development rather than infrastructure management. However, you will have less control over the underlying infrastructure and environment configurations, which might limit your ability to implement certain custom settings or software requirements. Additionally, you will be dependent on the platform’s capabilities and updates, which may not always align with your specific needs.

List any other needs you must change to suit your application requirements.
To use App Service effectively, I will need to ensure your application is compatible with its built-in features. This might involve refactoring your code to align with the platform’s requirements, which can help facilitate smooth deployment and efficient scaling. By doing so, you can take full advantage of App Service’s capabilities, such as automatic scaling, integrated monitoring, and streamlined deployment processes. This preparation will help ensure that your application runs seamlessly and can handle varying levels of demand without manual intervention.
