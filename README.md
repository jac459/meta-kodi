# meta-kodi

This repository contains supporting material for NEEO-Metadriver to control Kodi-applicatins over http (websocket).

Installation:

Two main files are required for installation:
A) Kodi-nodered.json; A Node-red flow that converts the NEEO-Metadriver buttons for Kodi towards the Kodi-player.
B) Kodi.json; The button definitions for NEEO-Metadriver.

We start by installing the flow into Node-red.
1) Download A) (Kodi-nodered.txt) to your computer and save it.
2) Open Node-red GUI in your browser (<IP-address BRAIN:1880>)
3) In the top-right of the Node-red GUI, you'll see a sub-menu icon (3 horizontal lines). Click that icon and choose import.
4) In the import dialog, at the bottom select "New flow", then click on "Select a file to import".
5) Navigate to the location where you saved A), select it and click on the red button "Import" in the import-dialog. Move your mouse to place all nodes and wires in the flow and place them.
6) Chek for any warning- or error-messages. If not, the flow is imported. You can give it a nie name, by double clicking the name in the TAB, then choose rename (you can delete it here a well).
7) Next step is configuring the IP-addresses in this flow: the Brain's IP-address (and Kodi's IP-address.  Change the flow's IP-address for brain (left-top node, called "[ws] NEEO-BRAIN") by double cliking on it; you'll see the properties for websocket-Meta.
8) Next to "URL", you'll see the currently defined IP, with at the right a pencil-iconm. Use that icon to change the IP-address into the address of your own NEEO-Brain. Confirm the change and confirm again. 
9) Do the same for the KODI-node, at the right bottom of the flow, specifying Kodi's IP-address.
10) Important!! Changes in flows aren't active directly, but only AFTER deplohying the flow. Node-0red GUI tells you that you've got changes pending when the "Deploy"button at the right top-corner is highlighted red. Click the button and Node-red will try to deploy the changes.  

Now the flow is created and customized, we can add the Kodi-driver to the Brain through the METAdriver. This process is very simple: 
11) On the NEEO-remote, select the META-device, go to settings and select Library. Scroll through the list and select Kodi, then click on activate. This will enable the Kodi-driver. 
12) Now use the normal NEEO-commands to create you Kodi-device with the Kodi driver we've just avtivated. Don't forget to "Unhide the recipe" and give it a nice name, with the shortcuts you want to use for Kodi.  

If you want to make changes to the NEEO-buttons in this driver, you can use the file Kodi-json and activate this via the user activation folder. 

Supported buttons and functions

This is the first release of Kodi-driver. It contains all you normally need to control a Kodi player.
The following Buttons are defined and mapped to functions in Node-red:
- "POWER OFF"; will shutdown the system where Kodi-player is running
- "VOLUME UP" & "VOLUME DOWN"
- "CURSOR UP", DOWN, LEFT & RIGHT"; navigating the cursor
- "PAGE UP & DOWN"; navigating an entire page
- "CHANNEL UP & DOWN"; same as "PAGE UP & DOWN"
- "PLAY"; context-aware... while playing: pause and play, otherwise "select"
- "STOP"; stop the current player
- "LANGUAGE"; Opens window for synchronizing the subtitles (start earlier or delay them); back to exit
- "SUBTITLE"; Opens the subtitle-submenu. Allows browsing, downloading, enabling subtitles
- "PAUSE"; pause or play while playing
- "BACK"; exit a submenu or go up one level in a list/window dialog
- "MENU"; context-aware... while playing: activates OSD, otherwise "context menu"
- "SELECT"; general select
- "MUTE TOGGLE"; silence the player.