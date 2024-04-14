<h2>Sharing Files. The setups</h2>

<h3>the MOST basic way:</h3>
right click the folder you want to share, select properties, click advanced sharing and tick the box. that's it!
<img src="https://i.imgur.com/warimfi.png">

now if we are looking for that folder on another machine in the network...
there it is!
<img src="https://i.imgur.com/aPUeeGs.png">



<h2>The Server Manager Way</h2>
In the server manager we have the option of going to "File and Storage Services" to manage our file shares.

<img src="https://i.imgur.com/mpvoOFv.png">
<br>
In this window we have several "profiles" to choose from.
<li>SMB (Server Message Block) is the standard protocol for sharing files on windows. There's a quick, advanced and applications option to choose from.</li>
<li>advanced only works with the file server resource manager and applications is used for hyper-v for example</li>
<li>NFS is used to share to and from UNIX devices</li>
