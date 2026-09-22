- Appears as stuck or unresponsive print jobs; Printer not processing additional jobs; error messages in print queue
- **Issue may be with printer spooler**
	- **Printer Spooler** = Middle point between app and printer, app sends print job to spooler, spooler sends print job to printer
	- **Corrupted print jobs** will **cause** **spooler** to **crash** **or** **freeze**
	- Most spooler configs will automatically restart on failure
		- e.g. on Windows First failure = restart, Second failure = restart, third failure = no action and requires human intervention
- **Issues are logged**
	- Check **Windows Event Viewer** -> **Windows-PrintService** for corruptions or any issues are happening
- A single job might be causing the issues
	- Once Spooler fails nothing else in queue will be printed
	- Monitor print queue for details
		- Admins can delete or move a print job to the back of the queue to allow other print jobs to finish first before troubleshooting the problematic job

- **Clear Print Queue** <- Open printer settings and cancel stuck job or move to back of queue
- **Restart Print Spooler Service** (Windows) <- "Services" Window -> "Print Spooler" -> Right-click and restart
- **Update Printer Drivers** <- Download and Install latest drivers from manufacturer's website
- **Check for corrupt Jobs** <- Identify and remove problematic documents from print queue

