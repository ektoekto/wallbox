This is an example flow/code on how to control wallbox chargers directly with a function node. No need to install additional functions. Feel free to copy any part of it to your own needs. 
![kuva](https://github.com/user-attachments/assets/628d70f7-a782-411b-a05a-6bb9610a256e)

Modify the wallbox com function with your credentials and it should work. 

You can control the function by sending it a msg.payload.command where the value is the action.
Next actions are supported
- lock
- unlock
- pause
- resume
- reboot
- status
- update


You can specify which charger you want to control by adding msg.payload.parameter and msg.payload.value
![kuva](https://github.com/user-attachments/assets/c4c310db-c7f7-4f6e-a32e-fb78cdac9976)

without these the command is applied to all the chargers, like if you want to unlock all of them at once.


You can check from the global object what parameters and values are there:

![kuva](https://github.com/user-attachments/assets/7bd8c835-4e98-4a3f-800f-1c24622ab8ce)


This flow also supports http in, for example you can build an IOS shortcut and give the parameters in the address line
![kuva](https://github.com/user-attachments/assets/a29f833c-a980-4778-9e5d-842ec9a34874)

This shortcut sendout an unlock command when I arrive to my workplace. The function returns a text "unlock was successful" that the shortcut then reads outloud. In order to send http to nodered, you need to have the basicAuth in the request parameters. 
