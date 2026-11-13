# LunaGC-6.6-Repair
Fixed some errors in the original warehouse
LunaGC-6.6.0
Important note
This is an experimental 6.6 branch containing changes catered to fix some gameplay aspects related to farming and building characters for the heck of it.
Protocol buffer definitions can be found on GitLab, including translations.
Updated version of Grasscutters, with some new features implemented.
Features and functionality of the PS is not guaranteed, try it yourself to see what works and what doesnt.
This is possibly the only public PS with updated mob and gadget spawns, including custom fallback mob spawns for otherwise unsupported post-5.4
overworld regions.
Read the handbook!
Setup Guide
Read it below, its just enough to get the server up and running along with the client.
Main Requirements
Get Java 17
Get MongoDB Community Server
Get NodeJS (For handbook generation)
Get game version REL6.6.0
Make sure to install java and set the environment variables.
Build the server (refer to "Compile the actual server" in this guide.)
Install the resources using one of these methods:
Regular method: Download the Resources, create a folder named `resources` inside the LunaGC folder, and extract the resources into it.
Resource cache method: Download `LunaGC-6.6-resources.cache` from the latest Resource Cache release, create a folder named `cache` inside the LunaGC folder, and place the file inside it without extracting or renaming it.
The server will automatically use a valid resource cache when available and fall back to the normal `resources` folder otherwise.
Set useEncryption, Questing and useInRouting to false (it should be false by default, if not then change it).
Patch the game
Start the server and the game, make sure to also create an account in the LunaGC console.
Have fun!
Patching the game
Put Astrolabe.dll in the game folder at `GenshinImpact_Data/Plugins`. Make sure you back up the old `Astrolabe.dll` in the plugins folder.
To "disable" the patch, just rename Astrolabe.dll to something else so it's not a DLL or don't name it Astrolabe (for example Astrolabe.deleleu / astrollable.dll).
If you use Cutivation, put the file in the `Cultivation/patch` directory and rename it to `6version.dll`. Make sure you also back up the original dll before replacing it.
Getting started
Clone the repository (install Git first )
```
  git clone https://github.com/Rafs-kk/LunaGC-6.6.git
  ```
Now you can continue with the steps below.

Compile the actual Server
Requirements:
Java Development Kit 17 | JDK or higher
Sidenote: Handbook generation may fail on some systems. To disable handbook generation, append `-PskipHandbook=1` to the `gradlew jar` command.
For Windows:
```shell
  .\gradlew.bat
  .\gradlew.bat jar
  ```
For Linux:
```bash
  chmod +x gradlew
  ./gradlew
  ./gradlew jar
  ```
You can find the output JAR in the project root folder.
Manually compile the handbook
```shell
./gradlew generateHandbook
```
Troubleshooting
Make sure to set useEncryption and useInRouting both to false otherwise you might encounter errors.
To use windy make sure that you put your luac files in C:\Windy (make the folder if it doesnt exist)
If you get an error related to MongoDB connection timeout, check if the mongodb service is running. On windows: Press windows key and r then type `services.msc`, look for mongodb server and if it's not started then start it by right clicking on it and start. On linux, you can do `systemctl status mongod` to see if it's running, if it isn't then type `systemctl start mongod`. However, if you get error 14 on linux change the owner of the mongodb folder and the .sock file (`sudo chown -R mongodb:mongodb /var/lib/mongodb` and `sudo chown mongodb:mongodb /tmp/mongodb-27017.sock` then try to start the service again.)
Credit
Proto Repository hk4e-protos
Patch Repository hk4e-patch-universal
Original Repository kitkat033Additional note: This repository has not been restored from the original one. It did not have complete functions before. Resources and the game itself need to be downloaded from it. It's worth mentioning that the encryption key has been removed in this version
https://github.com/Rafs-kk/LunaGC-6.6

