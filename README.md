# simple minecraft server
#### MINECRAFT 1.12.2 SERVER REPO
there also could be minecraft_server.1.12.2.jar, forge-1.12.2-14.23.5.2860.jar & world, mods, orbis, .mixin.out, libraries


forge doesnt transfer mods from server to client.

requires having all mods from requirements.txt installed on client (C:\Users\user\AppData\Roaming\.minecraft\mods)

# oh my god is that a tutorial on forge minecraft server
to do the same server you have to:
- decide minecraft version for the server(but this md is for 1.12.2 sooo...)
- install Minecraft Forge for that version
- install JDK 8(this jdk version is for 1.12.2)
- create folder for the server(e.g. D:/SERVER)

after you launch Minecraft Forge, you pick the "install server" option & path to the folder you created for server. when you open that folder, you should see "libraries", "forge-1.12.2-14.23.5.2860.jar"(or newer) and "minecraft_server.1.12.2.jar". there also could be "1.12.2.json".

now you should create start.txt and insert there this command:

<i>"C:\Program Files\OpenJDK\jdk-8.0.262.10-hotspot\bin\java.exe" -Xmx1024M -Xms1024M -jar forge-1.12.2-14.23.5.2855.jar nogui"</i>

- "C:\Program Files\OpenJDK\jdk-8.0.262.10-hotspot\bin\java.exe" is a JDK 8 path on Windows
- -Xmx1024M is the MAX number of MB of RAM available to the server
- -Xms1024M is the amount of RAM that the server will occupy at the server start
- -jar forge-1.12.2-14.23.5.2855.jar is Forge version. be careful to insert your current version of Forge
- nogui disables the server window that shows amount of players and server load graph. you can use gui if your processor is strong

and so, you save start.txt with this command and rename it to start.bat. you should launch the .bat and see that few files are added at the server directory. DONT close the console, it'll close by itself. inside the eula.txt file you change "eula=false" to "eula=true".

if there are'nt new files added, you may've done those mistakes somehow:
- installed wrong version of Java
- used wrong path to OpenJDK
- just copypasted "-jar forge-1.12.2-14.23.5.2855.jar" into start.bat, when your actual forge version(in the server folder) is newer

if there's another kind of mistake, you should add "pause" one line below in start.bat to see an error message and explore it, so it looks like this:

<i>"C:\Program Files\OpenJDK\jdk-8.0.262.10-hotspot\bin\java.exe" -Xmx1024M -Xms1024M -jar forge-1.12.2-14.23.5.2855.jar nogui"</i>

<i>pause</i>


after succesfully editing eula.txt, you launch start.bat again. many files will be added about that. one of them is server.properties, where you can:

- set online-mode=true to online-mode=false to have access to the server without licensed minecraft
- see the port and the ip-address to connect to the server, e.g. server-port=11111, server-ip=1.1.1.1(you connect by 1.1.1.1:11111)
- allow nether, pvp and etc.

to add mods you should install them on the server and on the client: 

#### E.G. SERVER

<i>D:\SERVER\mods</i>

#### E.G. CLIENT

<i>C:\Users\user\AppData\Roaming\.minecraft\mods</i>

- the server and the clients should have the same Forge version
- same with the mods
- ...and some mods doesnt support working online
- ......btw all of the errors are in logs folder

to delete mod you firstly delete it from the server folder and then launch start .bat, where the server will ask you to completely delete this mod "/fml confirm" or cancel and shut the server down "/fml cancel"


and it's always better to stop server by /stop command, not by closing the cmd window.
