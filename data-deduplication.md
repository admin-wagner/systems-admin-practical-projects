<h2>Data Deduplication</h2>

As the saying goes, time and storage space is money. So let's not waste any.

In an office environment, lot's of data will be duplicated a lot of the time. For example if User1 downloads a copy of "project-info.txt" and Users 2-300 do the same thing. 
That unaltered textfile will be on everyone's machine, wasting precious precious space. With deduplication we can make it so that each user will only get a pointer to that file and it won't
be copied over 300 times. A great idea in this case!
<br> <br>
Let's start with adding the feature in our server manager.
<br>
<img src="https://i.imgur.com/IJQlxHJ.png">
<br><br>
Now that the role is enabled, we can configure data deduplication on our volumes like so:
<img src="https://i.imgur.com/fIokBe6.png">
<br><br>
And here is the settings window. You can choose what kind of server you want to deduplicate your file on - I chose general purpose file server for this test.
The other options are Virtual Desktop Infrastructure (VDI) Server and Virtualized Backup Server.
Importantly, you can choose to exclude file extensions and folders from deduplication. Generally speaking you don't want to deduplicate files that are being changed a lot, such as 
databases. Performance slowdown being the main reason.
So in this example I created a folder "Dont Dedup" and placed it into the excluded folders section.
<img src="https://i.imgur.com/88CSm4r.png">
<br>
<br>
To test out our deduplication storage saving magic, we're going to go into that settings window again, set the days to 0 and create a big file in our dedup folder and copy that file over to 2 other folders.
<img src="https://i.imgur.com/KkUSZu0.png">
<br> <br>
Now let's trigger the deduplication manually by typing this command into powershell:
<br>
<i>Start-DedupJob -Volume E:\ Optimization </i>
<br>
It will run for a while and when it's done this is what we see:
<br>
<img src="https://i.imgur.com/RQP4ldq.png">
<br>
The data saving implications are big and interestingly, as we can see, the fact that this happened is hidden from the user himself. 
Another little secret for the benevolent administrator...
