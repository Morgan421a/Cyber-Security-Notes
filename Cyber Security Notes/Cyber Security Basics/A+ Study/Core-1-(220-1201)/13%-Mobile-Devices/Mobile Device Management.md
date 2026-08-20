### Mobile Device Management (MDM)
- Used to manage company-owned and user-owned mobile devices
	- e.g. BYOD - Bring Your Own Device <- e.g. an employee brings their own device to work
- Allows for centralised management of the mobile devices
- Specialised function which requires specialised software to do so
- Allows system-admins to set rules and parameters regarding how the mobile devices are used, such as:
	- Set policies dictating what apps are allowed or not
	- Configuration or disabling of cameras and GPS
- Can be used to manage the whole device or set up a partition on a personal device allowing the user to maintain their own private data which is protected from company view
- Allows for the requirement of use for certain security policies
	- e.g. requiring all of the devices in the company to use screen locks and PINs to unlock the phone
##### BYOD
- Bring Your Own Device
	- Sometimes called "Bring Your Own Technology"
- Employee owns the device
	- Needs to meet the company's requirements
- More difficult to secure:
	- Both a home and work device
		- Needs to be decided what part of the device is private and what part is used for work
	- Can set parameters regarding how data is protected on the device
	- Set policies on what happens if the phone is upgraded, traded in, sold, or lost
##### COPE
- Corporate Owned, Personally Enabled
- Company buys the device
- Used both as a corporate and a personal device
- Organisation maintains full control of the device
	- Akin to company owned laptops and desktops
- Information is protected via corporate policies; data can be deleted at any time
- Company decides: 
	- How info is stored on device
	- What info is stored on the device
	- What happens to the stored data if the device is changed or lost
- **Choose Your Own Device (CYOD)**
	- Similar to COPE but user can choose from an offered range of devices

### MDM Policy Enforcement
- Allows for the config of corporate settings across all phones through the MDM console
	- Reduces need to configure each phone individually
- Require Two-Factor authentication
	- Require specific authentication types
- Manage Corporate Apps
	- Restrict or allow app installation
	- Install specific apps automatically
	- Prevent unauthorised app usage

### Mobile Device Synchronisation
- Many settings are already pre-configured such as:
	- Telephone information
	- Messages
- MDM allows for the central configuration of email settings because:
	- Everyone handles email services differently
	- Corporate email configs can vary
- MDM allows for specification of how data is synchronised such as If it'll be synced only over the Wi-Fi network or the cellular network too
	- Important for data backup and recovery
##### Synchronising data
- MDM allows for the config of:
	- What types of data will be synced e.g. Calendar settings, Contact details, etc.
	- Data Caps and Transfer Costs e.g. cost limitations only make syncing over 802.11 viable, cellular sync may be too costly for the org
	- Verifying data restrictions with the wireless carrier
	- Enable or Disable network connections e.g. automatic downloads on cellular data or the size allowed