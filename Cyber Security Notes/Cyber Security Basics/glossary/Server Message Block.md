---
aliases:
  - SMB
  - smb
---
- System Message Block

- Protocol that allows devices on the same local network (or connected via VPN) to access files, folders and printers on each other directly without the need to download a separate copy, unlike FTP or cloud services do
	- File behaves as if local even if physically stored elsewhere on the network
	- same overall network, bunch of VLANs connected to one main router = smb works
	- Same VLAN, devices connected to same switch = smb works
	- ^ same with LAN
	- different overall network entirely i.e home = smb won't work

- *Not to be confused with cloud services which store the files on a distant company's server*
- *Not to be confused with FTP which transfers a full copy of the file to a device*