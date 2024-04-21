<h2>Imagine the following...</h2>
You run an office and one of your IT people quits. He had access permissions to certain files that now need to be modified, but he didn't bother 
to give you his password and you're out of contact.
<br> 
What now?
<br><br>
<img src="https://i.imgur.com/x1TjVx7.png">

<br><br>
Open up cmd with "run as administrator" and enter the following:
<br><br>
<i>takeown /f "path_to_file"</i>
<br><br>
<img src="https://i.imgur.com/byrSnpY.png">
<br><br>
Now you took ownership of the file and you can access the security tab to make changes to permissions!
