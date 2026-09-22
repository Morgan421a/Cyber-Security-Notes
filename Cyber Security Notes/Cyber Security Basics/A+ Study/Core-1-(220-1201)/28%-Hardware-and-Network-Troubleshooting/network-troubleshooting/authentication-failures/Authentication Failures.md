- Occur when a user, device or app can't verify its identity to access network resources
- **Caused by**:
	- **Incorrect credentials**
		- Permission may be required to access certain resources on a network
			- Typically requires the proper credentials (Username, Password, other factors)
	- **Config mismatches**
		- Incorrect domain, server address, or port settings
		- Misconfigured **RADIUS** (Remote Dial-In User Service) or **LDAP** (Lightweight Directory Access Protocol) settings
	- **Expired or Revoked Credentials**
		- Authentication may time out and the connection needs to be refreshed in order to log back in
		- Locked accounts after multiple failed login attempts
		- Account disablement by admins
	- **Network Issues**
		- Connectivity problems stopping access to authentication servers
		- Firewall misconfigs blocking authentication traffic
		- DNS failures affecting server reachability
	- **Certificate Issues**
		- Expired or revoked certs
		- Mismatched or improperly installed certs
		- Untrusted **Certification Authorities** (CAs)
- Authentication may be a part of a service or background process
	- Difficult to see, error messages or feedback may not be seen if authentication doesn't work
- **Symptoms** of Authentication Failure:
	- **User Facing Symptoms**:
		- Error messages, e.g. "Access Denied", "Authentication Failed", etc.
		- Inability to login to apps, Wi-Fi networks, or shared drives
		- Repeated credential prompts despite correct inputs
	- **Admin Symptoms**:
		- Logs showing failed login attempts
		- Account lockout alerts triggered by excessive failures
		- Users reporting inability to connect despite correct credentials

- **Perform a packet capture**
	- Verify connectivity and look for errors
- **Troubleshooting Steps**:
	1. **Verify Credentials** <- Confirm correct ones used; account for case sensitivity; test credentials on different app or device
	2. **Check Account Status** <- Ensure account is active and not locked; Check if password has expired or the account is disabled
	3. **Inspect Network Connectivity** <- Use utilities such as `ping`, `tracert`, or `nslookup` to test connectivity; Ensure firewall rules aren't blocking auth requests
	4. **Check Server Configs** <- Confirm correct RADIUS or LDAP settings including IP, ports, and shared secrets; Verify correct domain and auth protocols are in place
	5. **Review Validity of Certificates** <- Ensure certs are valid and installed correctly; Check for trust in the Certificate Authority (CA)
	6. **Monitor Logs** <- Analyse logs for errors and trends; Look for failure patterns, such as repeated rejections
	7. **Reset or Re-issue Credentials** <- Provide a temp password or unlock the User's account; Advise Users to create stronger, memorable passwords
	8. **Update or Reconfigure Authentication Policies** <- Confirm MFA settings and security policies are appropriate; Adjust overly strict policies if needed

- **Carry out regular Config Audits**
	- Review auth server settings
	- Ensure compatibility with client devices and apps
- **Educate Users**
	- Train on identifying phishing attempts
	- Encourage secure credential storage practices