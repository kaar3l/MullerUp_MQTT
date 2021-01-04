# Specifications
MullerUp Cattle feeding robot had interface through HP iPaq device (Windows Mobile 6). Windows mobile was unstable and crashed from time to time. Then also getting new Windows Mobile device was getting harder every year.

The connection between MullerUp robot and the handheld device was with bluetooth. Firstly I tried to "view" what the robot was sending to the handheld device. The robot sends to the device simply raw text through bluetooth. Parsing this text is simple to get the data on the screen. One on the problems was that the connection would stay alive for about 5 seconds and then disconnect.

Then I soldered and programmed an arduino+HC06 bluetooth module to read what the handheld device is sending to the feeder. It seems that the mobile device is sending some keep alive message about every second. The message is "?".

So I captured what the device sends after connecting the device:
;E??????????

Then I captured all the data that the buttons are sending to the device:
| Number | Button | ->  | Message | bytes |
| :---:  | :---:  | :-: | :---:   | :---: |
| 1 | F | -> | F | 0x46 |
| 2 | x | -> | * (Multiplication sign) | 0x2A |
| 3 | + | -> | + | 0x2B |
| 4 | = | -> | = | 0x3D |
| 5 | % | -> | % | 0x25 |
| 6 | / | -> | / (Division sign) | 0x2F |
| 7 | - | -> | - | 0x2D |
| 8 | I | -> | Q | 0x51 |
| 9 | 7 | -> | 7 | 0x37 |
| 10 | 8 | -> | 8 | 0x38 |
| 11 | 9 | -> | 9 | 0x39 |
| 12 | II | -> | A | 0x41 |
| 13 | 4 | -> | 4 | 0x34 |
| 14 | 5 | -> | 5 | 0x35 |
| 15 | 6 | -> | 6 | 0x36 |
| 16 | III | -> | println? | 0x0D |
| 17 | 1 | -> | 1 | 0x31 |
| 18 | 2 | -> | 2 | 0x32 |
| 19 | 3 | -> | 3 | 0x33 |
| 20 | up | -> | W | 0x57 |
| 21 | 0 | -> | 0 | 0x30 |
| 22 | C | -> | C | 0x43 |
| 23 | Opc | -> | O | 0x4F |
| 24 | down | -> | S | 0x53 |
