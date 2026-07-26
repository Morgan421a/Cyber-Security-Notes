**Car Park**
- Cloud virtual computer === virtual machine? -> sort of, VM = the technology used to make them, Virtual Computers = created by a VM to give clients access to someone else's hardware resources over the internet

**What is the Cloud?**
- A service which lets a client use computing resources over the internet
- Allows IT resources to be flexible, cost-effective and easier to manage
- Has Many benefits for applications, including:
	- **Scalability** - Apps can be easily scaled up or down as their needs change
	- **Pay only for what is used** - Charged based on usage not upfront costs
	- **On-demand-self-service** - Servers and storage can be changed or removed without waiting for hardware
	- **Security** - Cloud providers protect the infrastructure  with strong security measures
	- **High availability** - Apps keep running even if part of the system fails
	- **Global Access** - Apps on cloud can be accessed by users anywhere in world

- Different types of cloud and cloud deployment methods exist, each serving their own purpose and being suited to different organisational sectors:
	- Deployment types:
		- Public Cloud - Most common, good for websites and global apps due to its affordability, ease of scale and no need for infrastructure management. -> Preferable for every use case
		- Private Cloud - Typically used where sensitive data is intended to be stored or used such as in the medical sector, gives owners more control, customisation and compliance for sensitive data
		- Hybrid Cloud - Used by companies such as e-commerce whereby private sensitive data needs to be kept from users but the app needs to remain scalable on the public side during high demand

	- Main Cloud service models:
		- Infrastructure as a Service (IaaS) - Clients rent computing resources such as virtual servers, storage and networking and manage the OS and their application while the cloud provider handles the hardware resources
		- Platform as a Service (PaaS) - Cloud provider manages the infrastructure while the client focuses solely on the application
		- Software as a Service (SaaS) - Cloud provider manages everything, clients access software over the internet through a browser or app i.e. Gmail or Zoom

- Major Cloud Vendors - AWS is currently the most popular due to its extensive offerings and global reach, but many providers exist:
	- Microsoft Azure
	- Google Cloud Platform (GCP)
	- Alibaba Cloud
	- IBM Cloud
	- Oracle Cloud
		- Each Vendor offers a range of services but AWS is still the most popular due to its vast infrastructure and support for businesses of all sizes


**Basic AWS Cloud Terminology**
- EC2 (Virtual Computer/Server) - Represents Virtual Computer in the cloud, has a CPU and RAM and can run apps (like real computer)
- Instance Type (i.e t2, t3, m5) - Describe how powerful the EC2 is, some have more RAM and CPU so are more expensive, instance type can be chosen depending on needs:
	- Bigger instances = more power + higher cost
	- Minor instances = less power + lower cost


## **Summary**
- **Cloud** - Using computing resources over the internet instead of local hardware
- **VMs vs Virtual Computers** - A Virtual computer/server is a machine that runs using another physical computer's hardware resources virtually. A VM is the technology upon which Virtual Computers/Servers are built
- **Cloud Server** - Provided by cloud service providers (AWS, GCP, Alibaba Cloud), enables clients to access the cloud, allowing them to create, host or use services on a cloud virtual computer without the need to purchase and configure their own physical servers.
	- Reduces the costs for individuals and orgs by removing the upfront hardware cost of a server and using a "Pay-What-You-Use" model (Costs depend on client's resource use on the cloud server) <- **Pay for what you use**
	- Widely available across the globe. Allowing clients on different sides of the world to use and interact with the same service on a cloud server. <- **Global Access**
	- Scalable, allowing virtual resources for a virtual computer to be adjusted as demand for a service/app shifts without the need to interact with physical hardware <- **Scalability**
	- Apps can keep running even if another service/part of the cloud server fails <- **High Availability**
	- Provide better app/service security by adding another layer of protection for the hosted services in the form of the cloud provider's own security infrastructure <- **Security**
	- Clients can change or remove servers without having to wait for hardware <- **On-Demand-Self-Service**

- Three cloud deployment models:
	- **Public cloud** - Good for websites and global apps, most common, cheapest, allow for scaling of resources as traffic shifts
	- **Private cloud** - Good for private sector orgs such as health sector or government, Allow for more customisation, control and compliance regarding how sensitive data is handled
	- **Hybrid cloud** - Good for services such as e-commerce where both private and public data is handled, allow for public and private data to be separated such that private data is protected from user view but public resources can still be scaled up or down to meet demand

- Different cloud management types:
	- **Infrastructure as a Service (IaaS)** - Cloud Provider simply gives the resources, responsibility of the app/service and the OS fall to the client
	- **Platform as a Service (PaaS)** - Cloud provider gives resources and controls the OS/general infrastructure, client only builds and controls the app/service
	- **Software as a Service (SaaS)** - Cloud provider creates and hosts their own app/service on the cloud through which clients can interact and use it over the internet

- Many cloud providers, a few being:
	- **Amazon Web Services (AWS)** * <- Most popular due to vast features and flexibility which suits a wide range of clients, from individuals all the way up to large orgs
	- **Microsoft Azure** * <- Closest competitor to AWS
	- **Google Cloud Platform (GCP)**  * <-  Big focus on AI, machine learning and analytics tools
	- **Alibaba Cloud** * <- Very popular in Asia
	- IBM Cloud <- Big focus on hybrid cloud and AI driven solutions for orgs
	- Oracle Cloud <- Focus on enterprise apps and databases
		- * = Most commonly used, providers most worth remembering

- AWS cloud platform:
	-  EC2 = represents a virtual computer/server on the cloud, each with provided their own virtual resources (CPU, RAM, Storage, Network)
	- Different instance types for each EC2, using tags to denote their power and costs (e.g. t2, m5). Bigger type = More Power + Higher cost

