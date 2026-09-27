This is a folder, containing a .zip file and .epcb
.zip file is to import the PCB to altium, and .epcb is a source file of the main PCB

Actually, .zip file(Altium) contains every file of the project, such as .schdoc and .pcbdoc

PCB_MyOwnMP3.pcbdoc - Main PCB Board
NFC.pcbdoc - NFC Board
PCB5.pcbdoc - IR Board

About .epcb I have no clue what you should do with it, but I have tested importing altium files into my EasyEDA Pro, and that worked quite well
<img width="2560" height="1304" alt="image" src="https://github.com/user-attachments/assets/66312530-75f3-4545-bf83-90518901b98c" />

Everything is good except the net port labels, I have no clue what happened to them:
<img width="1077" height="566" alt="image" src="https://github.com/user-attachments/assets/439cbfe3-a9c4-438a-ae4e-c65438796eac" />


Everything is also broken a little by little - the font didnt save, there is some strange PCB frame, some unknown 3D models, tho its not like that:
<img width="735" height="856" alt="image" src="https://github.com/user-attachments/assets/a5ed6d1d-320b-4b79-91fe-268642615740" />

And there are 15650 DRC mistakes ...
Tho to fix all it takes is to recreate the ground plane 
<img width="2557" height="1333" alt="image" src="https://github.com/user-attachments/assets/660f7d68-a0c9-407d-a02e-0932326e5808" />
