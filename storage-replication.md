<h2>Storage Replication between Servers</h2>

Add Roles and Features -> add feature "Storage Replica"
<img src="https://i.imgur.com/PdXnivL.png">

<br>
<br>
Bring some disks in through HyperV. We'll make one "Replica" and one "Logs" 
<img src="https://i.imgur.com/M9TqAH7.png">

<br>
<br>
Do this for your second server as well.
<br>
<br>
Bring the Disks online in "File and Storage Services".
Create Volumes from the hard drives. Make a replica and a logs volume on each server.
<img src="https://i.imgur.com/xU4xw8q.png">
<br>
<br>
After you set up the volumes on each server, make a folder on C:\ called "results", go into Powershell and type in this command: <br><br>

<i>C:\Users\Administrator> Test-SRTopology -SourceComputerName BLN-DC-1 -SourceVolumeName R: -SourceLogVolumeName L: -DestinationComputerName SVR-1 -DestinationVolumeName R: -DestinationLogVolumeName L: -DurationInMinutes 5 -ResultPath C:\results\  </i>

"BLN-DC-1" and "SVR-1" are the names of my 2 virtual servers.

<img src="https://i.imgur.com/YRwX0Nh.png">
<br><br>
This might take a while, but it will give you a report
