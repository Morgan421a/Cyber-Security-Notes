- Some compatibility exists between Operating Systems, such as sharing documents between different OS's
#### Hardware Compatibility
- OS hardware requirements need to be checked prior to installation
	- Different requirements between OS's
	- Newer systems (1 year old) tend to support latest OS's
	- Older systems (5+ years old) could potentially struggle with modern OS requirements
- **Windows 11 requires** Trusted Platform Module (**TPM**) **version 2** <- TPM 2
	- Cannot be installed if hardware doesn't have TPM 2
- RAM requirements MUST be met
- Legacy hardware may lack driver support for newer OS's
- Specialised tools or peripherals may need to be used in order to stay on older OS versions
#### Software Compatibility
- **Typically no direct app compatibility**
	- Executable from a Windows OS can't just be run on a Linux system
	- App must be written for the specific OS
	- Many software devs create a standard file format that can be moved between OS's without issue
	- Web-based apps can often be run in the browser regardless of the OS <- Bypasses OS compatibility issues
- Orgs may rely on legacy software, requiring older OS versions
	- e.g. Windows XP being used in engineering plants due to software limitations
- **Legacy Systems can be kept secure by isolating them from the internet**
#### Network Compatibility
- Most Systems communicate using TCP/IP protocol
- LANs allow different OS types to communicate
- Some OS types need a third-party server for file sharing
	- e.g. Windows and macOS can share files using a Linux or Windows file server
- OS features from the same family work better together
	- e.g. macOS AirDrop only supports Apple devices, not Windows
#### End-User Comaptibility
- Technicians typically work with multiple OS types:
	- Windows - 8.1, 10, 11, Server 2019/2022
	- Linux - Ubuntu, Kali Linux, CentOS
	- macOS
	- iOS and iPadOS
	- Android
	- Chrome OS
- Traditional users tend to only use one or two OS types
- Switching between OS's needs time to train and adapt
- Some similarities and distinct differences between OS interfaces
- Guidance may need to be provided to users when transitioning to a new OS within the workplace