<h2>Providing Redundancy Through Storage Pools</h2>

Redundancy is a big topic in all work environments. Catastrophic loss of data is the last thing that should ever happen. 
To manage our physical drives more efficiently we can make use of "storage pools" that allow us to put every gigabyte of every drive
in one big pool and allocate it as we wish. We can create dynamically expanding virtual drives out of that pool to meet our growing or shrinking demands.
We can also provide redundancy in case of drive failures.

In this example we created 3 drives in hyperv as stand-ins for physical drives. We gave them 8, 9 and 10 GBs. 
Now in server manager's file and storage services we can look at the situation:
<img src="https://i.imgur.com/smJMUEA.png">
