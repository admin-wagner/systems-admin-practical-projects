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
This might take a while, but it will give you a report on if replication is possible and how it would perform.
<br><br>
<img src="https://i.imgur.com/V9tjugo.png">
<br><br>
In my case it was very helpful to show me, that I needed to allow pinging in the firewall settings on SVR-1.

<br><br>
Everything else checked out though, so now we can create the Storage Replica Partnership in Powershell with this command:
<br><br>
<i>New-SRPartnership -SourceComputerName BLN-DC-1 -SourceRGName SR1 -SourceVolumeName R: -SourceLogVolumeName L: -DestinationComputerName SVR-1 -DestinationRGName SR2 -DestinationVolumeName R: -DestinationLogVolumeName L:</i>
<br><br>
"SR" meaning Storage Replica

<img src="https://i.imgur.com/LOptfUS.png">
<br><br>
That's it! The data you put into your primary replication drive on your Source Computer will be replicated to your secondary on your other server. You will, however, not be able to write to the drive on your secondary, as it's meant to act as a failover drive.
To make the secondary your into your primary (in case of disk failure of your primary for example) you can follow these steps:
<br><br>
Go to the server that has the secondary, go to powershell and type in this command:
<br>
<i>Set-SRPartnership -NewSourceComputerName SVR-1 -SourceRGName SR2 -DestinationComputerName BLN-DC-1 -DestinationRGName SR1 </i>
<br>
<img src="https://i.imgur.com/IAbmWbV.png">
<br><br>
Confirm your choice and you will be able to access the replication drive on this secondary, which is now you primary.
