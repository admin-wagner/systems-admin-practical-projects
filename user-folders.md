# Your user's very own drive

This is something every user will appreciate:  
Their own personal drive.  
Let's make it so that when the user logs in for the first time, a folder will be created in a domain shared folder, named after the user's 
account name and only be accessible to that user.  

## Setting up the shared folder containing all user folders

This one is easy.  
In the drive of your choice, create a folder, go to properties -> sharing -> advanced sharing -> tick the box and click ok  

![share folder](https://i.imgur.com/32wrRcz.png)  



Then create a folder inside that folder and call it something like "User Drives"  

On this one, you want to modify the permissions.  

Remove "Everyone" and add "Domain Users" and "Administrator". Give both of those groups full control.  

![user drives folder](https://i.imgur.com/uGnO27I.png)  




## Setting up the creation of a user drive when a user is connected to the domain

Navigate to your Group Policy Manager, create a GPO in the OU where youre users are located. Call it something like "Map Personal Drive"  
Edit this GPO and go here:  

![map drives](https://i.imgur.com/9jV2A5H.png)


Now follow these settings for your new mapped drive. Replace "BLN-DC-1" with the name of the server where your shared folder is located.

![now do this](https://i.imgur.com/aPCPCPj.png)


And that's it! Now as soon as you log in to the domain with a user account, a drive will be available for you and only you:

![personal drive](https://i.imgur.com/TvRdvKh.png)
