### Cloud Resources
- **Dedicated Resources** = Reserved exclusively for a single customer
	- Offers better performance, security, and greater customisation
- **Shared Resources** = Multiple customers use same physical infrastructure (e.g. servers or storage)
	- Resources isolated via virtualisation to ensure security
-  **Internal/Private** Cloud:
	- An **org/user builds** their **own private cloud**
		- Has their own dedicated resources
		- Pay for everything up front with no recurring provider fees (electricity, cooling, staffing, etc. still paid)
		- Install and manage everything themselves
- **External/Public** Cloud
	- An **org/user uses a public cloud created by others**
		- Shares resources on a public cloud with other orgs/users on the same cloud
		- Underlying infrastructure owned by a 3rd party
		- Cost can be metered (pay for what you use) or up-front (fixed rate)

### Metered and Non-Metered
- **Metered Utilisation**:
	- Pay for what you use:
		- Cost to upload data to the org - ingress traffic (Usually free)
		- Cost to store
		- Cost to download data to customers - egress traffic
			- Egress costs can be reduced by: 
				- Optimising file transfers and compressing data
				- Using Content Delivery Networks (CDNs)
				- Monitoring data transfer patterns and reviewing pricing models
	- Monthly costs can fluctuate depending on how much an org uses each month
	- Commonly used on the organisational side
- **Non-Metered Utilisation**:
	- Fixed price for certain amount of resources:
		- Pay for a block of storage (e.g. 2 GB)
		- No cost to upload
		- No cost to download
	- Commonly used on the consumer side

### Cloud Computing Characteristics
- **Elasticity** <- Resources can be scaled up and down as needed with ease (sometimes even automatically to meet demand)
	- Cloud enables instant resource provisioning
	- Removes need to purchase hardware for peak periods, reducing costs
- **Availability** <- Systems are almost always available thanks to many redundancies across separate cloud locations
- **File Synchronisation** - Data can be duplicated across cloud locations
	- May be built into an app/service to be managed by the customer
	- May be automatically handled by cloud infrastructure behind the scenes
- **Multitenancy** <- Many clients using the same cloud infrastructure simultaneously
	- Technologies, process, and procedures in place to maintain separation between customers
	- Allows cloud provider to offer an efficiency in both technology and costs by maximising resource utilisation