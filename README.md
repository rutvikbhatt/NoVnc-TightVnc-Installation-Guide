# NoVnc-TightVnc-Installation-Guide
1. Install [Tightvnc](https://www.tightvnc.com/), After installation set up a password for authentication.

2. Download node.js from [here](https://nodejs.org/en/)
(download the recommanded version)
After installation press Start and open node.js command prompt 

3. Run the following command in Node.js command prompt (ref. [npm.js](https://www.npmjs.com/package/@maximegris/node-websockify)): 	
```npm install --save node-websockify ```

4. Once the installation is finished create a folder named 'novnc' on desktop and create a subfolder named 'websockify'. Now download the [websockify.js](https://github.com/rutvikbhatt/NoVnc-TightVnc-Installation-Guide/raw/master/websockify.js) that is provided in the current repository:	

5. Now open the Node.js command prompt and type:
```
cd desktop
cd novnc
cd websockify
node websockify.js
``` 

***websockify part is completed and proxying***

6. Now download the latest version of [nginx](https://nginx.org/en/download.html?_ga=2.235179334.610747622.1588686511-49539150.1588686511)
for windows and copy paste it in the new folder named 'web' along side the 'websockify' folder 
Now open 'web' folder and find folder named 'html' and delete the two html files in this folder 
Now open [GitHub Repository](https://github.com/novnc/noVNC)
clone or download this file and copy paste it in the 'html' folder

7. Now open the command prompt and type
```start nginx``` 

8. Press start and click on start TightVNC server, Under the 'Access Control' tab and click on 'Allow loopback connections'

9. Open browser and type: 
```YOURIPADDRESS/vnc.html```
On the left side of the window, click on settings icon and then advanced settings. Click on websocket and add the details stated below:
(This detail needs to be filled only once)
```
Enter you IP adress as Host 
Port: 8000 
Path: websockify
```
10. Click on connect and your noVNC is working! 

***Note: This document is inspired from [this tutorial by JIBSIL](https://www.youtube.com/watch?v=NYEyyVDsapw).***
