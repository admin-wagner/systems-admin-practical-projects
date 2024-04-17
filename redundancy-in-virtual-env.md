<h2>Providing Redundancy Through Storage Pools</h2>

Redundancy is a big topic in all work environments. Catastrophic loss of data is the last thing that should ever happen. 
To manage our physical drives more efficiently we can make use of "storage pools" that allow us to put every gigabyte of every drive
in one big pool and allocate it as we wish. We can create dynamically expanding virtual drives out of that pool to meet our growing or shrinking demands.
We can also provide redundancy in case of drive failures.

In this example we created 3 drives in hyperv as stand-ins for physical drives. We gave them 8, 9 and 10 GBs. 
Now in server manager's file and storage services we can look at the situation:
<br>
<img src="https://i.imgur.com/smJMUEA.png">

<br>
From this window we can create a new storage pool, give it a name and choose all the drives to enter into our pool:
<br>
<img src="https://i.imgur.com/BCzUzkz.png">

as we can see, the storage space combines to a whopping 27gb.

Still in the storage pool window, we can now create some virtual disks from our pool, give them names and choose from the following options:
<li>Simple</li>
<li>Mirror</li>
<li>Parity</li>
<img src="https://i.imgur.com/3kFXoPa.png">
These reflect what you'd do with RAID so:
<i>The main difference between a mirror drive and a parity drive is that a mirror drive creates an exact copy of the data on another drive, while a parity drive uses parity information to reconstruct data in the event of a drive failure. Mirror drives provide high redundancy and fast read speeds, while parity drives provide better storage efficiency and can tolerate the failure of one or more drives (depending on the RAID level) without data loss.</i>
In this case we will choose mirror.
