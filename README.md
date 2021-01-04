# Hardware specifications
MullerUp Cattle feeding robot had interface through HP iPaq device (Windows Mobile 6). Windows mobile was unstable and crashed from time to time. Then also getting new Windows Mobile device was getting harder every year.

The connection between MullerUp robot and the handheld device was with bluetooth. Firstly I tried to "view" what the robot was sending to the handheld device. The robot sends to the device simply raw text through bluetooth. Parsing this text is simple to get the data on the screen. One on the problems was that the connection would stay alive for about 5 seconds and then disconnect.

Then I soldered and programmed an arduino+HC06 bluetooth module to read what the handheld device is sending to the feeder. It seems that the mobile device is sending some keep alive message about every second. The message is "?".

So I captured what the device sends after connecting the device:
- ;E??????????

Then I captured all the data that the buttons are sending to the device:
| Number | Button | ->  | Message |
| :---:  | :---:  | :-: | :---:   |
| 1 | F | -> | F |
| 2 | x | -> | * (Multiplication sign) |
