- **Port Flapping** = Network interface goes up and down (link light on and off) over and over again
	- Connection keeps going up and down
	- Degraded performance or packet loss
- **Commonly a physical issue**
	- Check the cable and connection for damage and proper seating
	- Check NIC <- May be unstable
	- Issue may be the switch interface
- **May be caused by external interference**
- **Solution**:
	- Check switch logs for port or status changes
	- Isolate and eliminate sources of interference
	- Configure switch settings to minimise auto-negotiation issues
	- Replace bad hardware or cables <- May require additional purchases or professional crews
- **Troubleshooting Steps:**
	1. Check physical connections <- Try using known good cables
	2. Ensure cable length not exceeded
	3. Identify possible sources of interference
	4. Monitor port status <- Use switch diagnostic tools to detect flapping ports or errors
