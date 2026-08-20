### **Volume Shadow Copy Service (VSS)**
- **VSS** -> coordinates the required actions to create a consistent shadow copy (AKA **Snapshot** or **Point-in-Time Copy**) of the data that is to be backed up
- **Volume Shadow Copies** -> Stored on the **System Volume Information** folder on each drive that has protection enabled
- **VSS** enabled == **System Protection** Turned on
- If **VSS** is enabled, following tasks can be performed from within **Advanced System Settings**:
	- **Create a Restore Point**
	- **Perform a System Restore**
	- **Configure Restore Settings**
	- **Delete Restore Points**

- Malware writers are aware of this feature and write code in their malware to look for and delete **Volume Shadow Copies**, making it impossible to recover from a **ransomware attack** unless an offline/off-site backup exists
- **Shadow Copies** can be configured by right clicking on a disk and pressing "*Configure Shadow Copies...*"