#### **Trees, Forests, and Trusts**
- Some organisations may need more than one domain
- Active Directory Supports the integration of multiple domains, allowing networks to be **partitioned** into units that can be **managed independently**
##### **Trees:**
- **Tree** = A method of joining multiple domains that **share the same namespace** together
	- e.g. splitting the `thm.local` domain into 2 subdomains for UK and US branches, building a tree with `thm.local` as the **root domain** and `uk.thm.local` and `us.thm.local` as the subdomains, each with its AD, Computers and Users
- A partitioned structure gives better control over who can access what in a domain
	- e.g. one subdomain's IT department will have their own DC that managed resources for their subdomain only. 
		- Domain Admins have complete control of each branch in their respective DCs but not other subdomains' DCs
	- Policies can be configured independently for each domain in the tree

- **Enterprise Admins** group = Security group that grants a user admin privileges over all of an enterprise's domains
	- Each domain still has their Domain Admins with admin privileges over their individual domains
	- **Enterprise Admins** can control everything in the enterprise

##### **Forests:**
- **Forest** = The **union** of multiple **trees** with **different namespaces** into the same network
	- e.g. Company acquires another one with a different name and namespace, connects both company's **trees** together to become a **forest**

##### **Trust Relationships**
- **Trust Relationships** = The way through which domains arranged in **trees** and **forests** are joined together
	- Allows for the authorisation of a user from one domain to access resources from another domain
- **One-Way Trust Relationship** - If `Domain AAA` trusts `Domain BBB`, a user on BBB can be authorised to access resources on AAA -> Simplest **trust relationship** to establish
	- **Direction** of the **one way trust** relationship is the **opposite** to that of the **access direction**
		- i.e. Fileserver trusts domain ->
		- domain is trying to access fileserver <-

- **Two-Way Trust Relationship** - Allows both users to mutually authorise users from the other
	- By **default,** **joining multiple domains** under a tree or forest will **form** a **two-way trust relationship**

- Trust relationship between domains **doesn't automatically** grant access to all resources on other domains
	- Once trust relationship established, option to authorise users across domains becomes available, but what is/isn't authorised can still be selected