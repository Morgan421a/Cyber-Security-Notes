###  Cloud Computing
- Allows apps and services to be hosted anywhere across the globe
- Effectively unlimited resources, only limited by the cost to use them
- Allows infrastructures to be deployed  and resources to be adjusted in minutes
	- Can be created and removed as needed
- Resources are flexible and can be adjusted to meet the current demand for an app or service
	- Cost is based on the amount of resources used <- Less wasted resources and therefore capital while still maintaining room for growth if needed
- Many public clouds located in key geographical locations, allows users to deploy apps or services on a cloud that best suits the target audience (i.e. an app intended for use by Europeans)

### Cloud Deployment Models
- **Public**:
	- Resources provided by service providers over the internet (i.e. Microsoft Azure, AWS, etc.)
	- Cost-effective and quick to deploy
	- Security deemed less robust compared to other models
	- **Best for cost savings and general accessibility**
- **Private**:
	- Cloud running in an org/user's own virtualised local data centre (e.g. healthcare, government, financial sectors)
		- Exclusive to a single org
	- Higher security and control
	- More expensive to build and maintain
	- **Good for orgs prioritising security**
- **Hybrid**:
	- Mix of public and private cloud, for example:
		- Private cloud used by an org to run their own internal apps and services on
		- Public cloud used by an org to allow deployment and access by users over the internet
	- Requires strict rules for data segregation and security
	- **Good for balancing data protection with cost-effectiveness**
- **Community**:
	- Several Organisations, with common needs, sharing a cloud and its resources amongst each other (e.g. Research, Education)
	- Reduces costs by pooling resources
	- Poses security challenges due to differing controls among orgs
	- Risk of inheriting security vulnerabilities from other connected orgs
	- **Good for collaborative groups with similar/shared goals**

### Infrastructure as a Service (IaaS)
- Sometimes called **Hardware as a Service (HaaS)**
	- **Includes hardware resources with or without a basic OS**
- Essentially renting hardware, on a cloud infrastructure, out to users
	- e.g. CPU and storage space
- Users responsible for the management and security of the app or service
	- e.g. User installs and maintains the OS, as well as maintaining the security of the system
- Cloud provider has access to the hardware, but data is solely under the control of the User
	- Grants slightly more security over other models but requires more work to manage and maintain
- Commonly used by Web Service Providers

### Platform as a Service (PaaS)
- Cloud Provider handles infrastructure, i.e. servers and software (such as the OS)
	- **Includes middleware and runtime environments** (e.g. databases, web servers, etc.)
- User solely handles development of the app or service to be run on the platform
	- Doesn't have direct control of the data, people, or infrastructure <- Trained security professionals deal with these
- User develops app from what's available on the platform <- Like putting building blocks together
- Example PaaS Cloud Service Provider = Force.com / Salesforce Platform

### Software as a Service (SaaS)
- On demand software
	- User logs in using credentials such as a Username and Password, typically through a web-based frontend, and can use a piece of software without needing to install it locally
- **Includes fully managed software apps**
- User doesn't manage the app/service or infrastructure
	- e.g. no need to worry about OS updates, managing software apps or code, or where the data is
- Cloud Service Provider manages app/service and infrastructure
- Offers a complete application, no need for a user to develop anything
	- Examples: Google Mail, Microsoft 365

### Responsibility Matrix

- ![[Pasted image 20260914113331.png]]