---
layout: post
title:  "Setting up a Mapped Network Drive in VirtualBox"
date:   2011-02-02 15:44:00
tags: backup virtualbox windowsxp
---

I've set up a Windows XP virtual machine in VirtualBox to do .NET development.  I want my work to be backed up by my host machine's backup software, but the 10GB virtual hard drives wreck havoc as the whole thing needs to be uploaded every time a single file on the virtual machine changes.  To avoid this, I've set up a shared folder in the VirtualBox VM configuration, and in the VM I've mapped the share to a network drive.  this way all the files on that mapped drive are stored on the file system of the host machine and can be backed up separately from the large virtual hard drive.

The steps were as follows:

1. Create a folder on the host machine to serve as the VM's network share (all mine are under ~/VirtualBox/Shares)
2. With the WinXP VM powered off, open up it's settings form the VirtualBox main console (right-click -> Settings)
3. Under 'Shared Folders', click the 'Add Shared Folder' button
4. Set the Folder Path to the folder you created above, note the Folder Name if you don't change it, and make sure the share is not marked as read-only.  Click OK.
5. Power on the VM.
6. In Windows Explorer, open the 'Folders' side panel.
7. Navigate to 'My Network Places -> Entire Network -> VirtualBox Shared Folders' and open the shared folder you configured above.
8. Note (or copy to clipboard) the UNC path to the network share (probably something like "\\VBOXSVR\[folderName]")
9. In Windows Explorer, choose "Tools -> Map Network Drive"
10. Pick a Drive letter, and paste the UNC path from above into the 'Folder' text box.  Ensure 'Reconnect at logon' is checked, and click 'Finish'.

Now you can open 'My Computer' and navigate to the drive letter you selected.  The mapped drive will be there every time you start the VM.

**Update 2/3/2011:** Originally I removed the optical drive from the VirtualBox VM configuration so I could add the shared network drive as D: and move the optical to E:.  But when I re-added the optical drive, the VM did not add the optical drive and had trouble mounting the network share to D:.  After some tinkering, I ended up with the optical drive back on D: and mapped the network drive to E:.  No trouble so far.
