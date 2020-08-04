# NoVnc-TightVnc-Installation-Guide
1. Install tightvnc from: https://www.tightvnc.com/ After installation set up a password for authentication.

2. Download node.js from: https://nodejs.org/en/
(download the recommanded version)
After installation press Start and open node.js command prompt 

3. Now open: https://www.npmjs.com/package/@maximegris/node-websockify 
Run this command in Node.js command prompt: 	
```npm install --save node-websockify ```

4. Once the installation is finished create a folder named 'novnc' on desktop and create a subfolder named 'websockify'. In this folder create a text document named 		'websockify.txt' and change its extension from .txt to .js and then copy paste the code below in the document:	
```
var websockify = require('node-websockify');
websockify({
source: '127.0.0.1:8000',
target: '127.0.0.1:5900',
});
```
5. Now open the Node.js command prompt and type:
```
cd desktop
cd novnc
cd websockify
node websockify.js
``` 

***websockify part is completed and proxying***

6. Now go to: https://nginx.org/en/download.html?_ga=2.235179334.610747622.1588686511-49539150.1588686511
Download nginx latest version for windows and copy paste it in the new folder named 'web' along side the 'websockify' folder 
Now open 'web' folder and find folder named 'html' and delete the two html files in this folder 
Now go to: https://github.com/novnc/noVNC
clone or download this file and copy paste it in the 'html' folder

7. Now open the command prompt and type
```start nginx``` 

8. Go to windows start TightVNC server under the 'Access Control' tab and click on 'Allow loopback connections'

9. open browser and type: 
```YOURIPADDRESS/vnc.html```
On the left side of the window, click on settings icon and then advanced settings. Click on websocket and add the details stated below:
(This detail needs to be filled only once)
```
Enter you IP adress as Host 
Port: 8000 
Path: websockify
```
10. Click on connect and your noVNC is working! 
