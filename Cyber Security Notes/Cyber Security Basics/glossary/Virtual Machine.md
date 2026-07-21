---
aliases:
  - VM
  - Lab Machine
---
**Car Park:** 

- Virtual Machine

- Software Based emulation of a physical computer
	- runs an OS and apps within and isolated enviro on a host machine
	- Managed by a hypervisor
	- Partitions physical resources like CPU, memory and storage allowing multiple guest OS's to run on a single physical server or desktop at the same time.

- Not completely isolated from main computer, only separated by logic not hardware therefore it is possible for malware to leak or escape to the main system using:
	- Hypervisor vulnies 
	- shared resources such as shared folders between the guest and host or inject code via the clipboard which bypasses the hypervisor entirely
	- Network bridging if the VM is on the same network segment as the host, network-propagating worms (like WannaCry) can attack the host just as they would any other computer on the LAN.
	- More sophisticated malware can detect a VM and hide its malicious intent and is more common than a leak. It checks for specific hardware IDs, registry keys or low RAM which is a typical sign of a VM.