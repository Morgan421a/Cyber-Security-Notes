##### **Kerberos Authentication**
- Default auth protocol for recent Windows versions
- Users logging into services using Kerberos are assigned tickets
	- Ticket = essentially proof of previous authentication
- Users with tickets can present them to services to show they've already authenticated into the network before and are therefore able to use it
- Kerberos process:
	1. User sends username and timestamp encrypted using a key derived from their password to the **Key Distribution Centre (KDC)** <- A service typically installed on the DC in charge of creating Kerberos tickets on the network
	2. KDC creates and sends back a **Ticket Granting Ticket (TGT)** <- Allows user to request additional tickets to access specific services
		- Allows for ticket requests without needing to pass credentials every time they want to connect to a service
		- KDC also gives the user a **Session Key** which is needed to generate the following requests
		- **Encrypted TGT includes copy of the session key as part of its contents, KDC has no need to store the session key as can recover copy by decrypting the TGT if needed**
	3. When user wishes to connect to a service on the network (e.g. share, website, database, etc.) they use their TGT to ask KDC for a **Ticket Granting Service (TGS)** 
		- **TGS** = Tickets that allow connection **only** to the specific service they were created for
		- To request TGS, user sends their username and timestamp encrypted using the session key along with the TGT and a **Service Principal Name (SPN)** <- **SPN** indicates service and server name user intends to access
	4. KDC sends TGS as well as a **Service Session Key** <- User needs to authenticate to the service they want to access
		- TGS encrypted using a key derived from the **Service Owner Hash** <- **Service Owner** = User/Machine account the service runs under
		- TGS contains copy of **service session key** on its encrypted contents so Service Owner can access it by decrypting the TGS
	5. TGS can then be sent to desired device to authenticate and establish a connection; service uses its configured account's password hash to decrypt the TGS and validate the Service Session Key

- **Kerberos Process in Brief:**
	1. User sends **username** and a **timestamp** **encrypted** using a key derived from their password to the **Key Distribution Centre (KDC)**
	2. **KDC** responds by creating and sending a **Ticket Granting Ticket (TGT)** as well as a **Service Key**
	3. User tries to connect to a service, uses their **TGT** to ask **KDC** for a **Ticket Granting Service (TGS)** by sending their **username** and a **timestamp** **encrypted** using the **Session Key** alongside the **TGT** and a **Service Principal Name (SPN)**
	4. **KDC** sends user a **TGS** and a **Service Session Key**; **TGS** encrypted using key derived from the **Service Owner Hash** and contains a copy of the **Service Session Key** no its encrypted contents, allowing **Service Owner** to access it by decrypting the **TGS**
	5. **TGS** can now be sent to desired service to authenticate and establish a connection; service uses its configured account's password hash to decrypt the **TGS** and validate **Service Session Key**