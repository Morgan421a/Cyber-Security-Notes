##### **Firewall & Network Protection**
- Shows 3 firewall profiles:
	- **Domain** - Profile applies to networks where host system can authenticate to a domain controller
	- **Private** - Profile is user-assigned, used to designate private or home networks
	- **Public** - Profile used to designate public networks e.g. WiFi hotspots at airports, coffee shops, etc.

- Clicking into each allows them to be toggled on/off as well as blocking all incoming connections when using that specific profile
	- **Recommended to leave on unless user is 100% confident in what they're doing**

- **Allow an app through firewall:**
	- Displays the current settings for public and private firewall profiles regarding what apps are allowed to communicate through them
	- Allows apps to be permitted or restricted from communicating through a particular firewall profile
		- Some apps provide more information if available through the `Details` button

- **Advanced Settings:**
	- `wf.msc` in run for quick access
	- Allows for the creation and configuration of firewall rules controlling both inbound and outbound traffic
