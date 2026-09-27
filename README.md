
<p align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="LOGO/black.png">
  <source media="(prefers-color-scheme: light)" srcset="LOGO/white.png">
  <img alt="SAIL THE PROTOTYPE LOGO" src="URL_TO_BLACK_IMAGE">
</picture>
 </p>

<h1 align="center"><b>SAIL THE PROTOTYPE</b></h1>

<div align="center">

<img src="https://img.shields.io/badge/License-MIT-brightgreen?style=for-the-badge">
<img src="https://img.shields.io/badge/Status-In--Development-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/Platform-STM32H7-blue?style=for-the-badge&logo=stmicroelectronics">

</div>

---


**SAIL The Prototype** is a [DMP](https://en.wikipedia.org/wiki/Digital_media_player), an open-source project that aims to become a startup. This is not a basic digital media player, but also a multi-tool. It has 433MHZ CC1101, [Infrared LED](https://www.lcsc.com/product-detail/C18199783.html), and NFC functions(13.56MHZ). 
The STM32H723 is a powerful MCU for that project, I would say it is even an overkill. 

Hardware Architecture:
  1. Main Board: Houses the STM32, ESP32, Display, and user input interfaces
  2. NFC Board: Contains the NFC circuitry, CC1101(currently 433 MHZ only), and magnetic pogo pin connectors
  3. Infrared Board: Dedicated to IR Transceiver

The goal of the project is to combine multi-tool device with a music player, making you less addicted and helps you to escape social media & algorithms(bad ones).


|*MAIN Board* Top Component Layer                                                                                                    |*MAIN Board* Bottom Component Layer                                                                                                              |  
|  :---                                                                                                                              |   :---                                                                                                                              |
|<img width="732" height="1012" alt="image" src="https://github.com/user-attachments/assets/6910aecf-bcad-42f6-b1f6-671b1048c61b" /> | <img width="754" height="1000" alt="image" src="https://github.com/user-attachments/assets/9ee13938-8767-4893-b497-99480a05d921" /> |

---

[![Click me!](MainBoardImage.png)](https://sail-mocha.vercel.app)
<p align="center">
    <b>Click the picture to see MAIN Board IBOM!</b>
  </a>
</p>

---


So, lets get into the details. First of all, lets talk about what you see here the most, to be exact - the user input devices.

The most valuable thing you can see here is probably the big [encoder](https://www.lcsc.com/product-detail/C160841.html). The encoder is pretty cool, its being used widely, especially at the automotive solutions. 

Its a 5-way button + encoder functions, to be exact its going 5 directions(X+, Y+, X-, Y-), pressing down, scrolling phase A and B. Next thing are 2 buttons, I still have no clue what I will use them for, but probably next song - previous song.

The most hidden, but probably the coolest thing of the device is the [thumb potentiometer](https://www.lcsc.com/product-detail/C351175.html), its placed at the left edge of the board, next to the left end to the display. 


---
<h1 align="center"><b>NFC Board</b></h1>


[![Click me!](NFC_image.png)](https://ibom-nfc.vercel.app/)
<p align="center">
    <b>Click the picture to see the NFC PCB IBOM!</b>
  </a>
</p>

--- 


NFC Board that contains half out of all of the functionality of the device --

It has NFC, CC1101 *433 MHz only yet*, and as a juicy cherry on a chocolate dry cake -
magnetic pogo pins for a breakout board. Here is the pinout if you would like to make a breakout board 

<img width="1071" height="945" alt="Untitled-2026-04-23-1610 excalidraw" src="https://github.com/user-attachments/assets/6f1c1e8d-ac0f-4287-952c-3f83fad0ff0e" />


| Pin on the board| IO on the ESP32|
| ------------------------------ | ----------------------------------- |
| CS1: | IO32 |
| CS2: | IO33 |
| CS3: | IO4  |
| CS4: | IO15 |
| | |
| MOSI: | IO23 |
| MISO: | IO19 |
| SCK:  | IO18 |
| CS:   | -    |
| | |
| SDA: | IO21 |
| SCL: | IO22 |
---
<h1 align="center"><b>Infrared board</b></h1>

[![Click me!](IR_BoardImage.png)](https://ibom-ir.vercel.app/)
<p align="center">
    <b>Click the picture to see the Infrared PCB IBOM!</b>
  </a>
</p>

---

I couldnt find any good IR Transceiver which was right angled, so instead I found a really good SMD 5050 LED, its powerful enough to remote something from the distance of 15m *by my calculations*

---
# 3D Design:

Here is an image how it looks from the side, I explained a big rectangular right there and a strange looking knob right there too
<img width="1950" height="1006" alt="image" src="https://github.com/user-attachments/assets/641eae26-620e-4c15-96ba-13c1fd798831" />

---

# Fusion360 Render:


<img width="986" height="931" alt="image" src="https://github.com/user-attachments/assets/ef67cda0-6f82-4c04-9052-216e3562510d" />

**The 3D files are in the Release folder since GitHub didnt want to accept files >25MB, there are 2 files, a Knob and fully assembled PCB(No casing yet)**

---

<h1 align="center"><b>More details and summary</b></h1>


| **Feature**                    | **Details**                                                                                                                                          |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Main MCU**                       | STM32H723 as a main MCU that does all the work                                   |
| **Secondary MCU**                  | ESP32-WROVER-IE(16MB) for BlueTooth headphones and pogo pin connectors(IOs)                                                                                             |
| **2.4" IPS TFT Display**           | 2.4" IPS Display connected via FPC, 8080 16-bit protocol. [BuyDisplay](https://www.buydisplay.com/2-4-inch-ips-240x320-tft-lcd-display-capacitive-touch-screen)                               |
| **Multi-Tool features**            | [NFC Module](https://www.lcsc.com/product-detail/C5267436.html), CC1101 *433 MHz ONLY*, IR Transceiver, Receiver                |
| **RTC**                    | BS-CR2032-8 battery slot for [RTC functionality](https://www.lcsc.com/product-detail/C9866.html), and MAX-M10S-00B(GPS component) for RTC Syncing                       |
|	~~**Metal Body**~~                 | ~~Aluminium front and back plate; 3D-printed middle section~~ *plan for future*                                                                                              |
| **Power and file transmitting**    | USB-C Port which allows high speed data transfer(up to 50MB/s) with help of [USB3300](https://www.lcsc.com/product-detail/C108954.html) , and of course power delievery                                             |
| **Battery Type**             | 2500mAh Li-Po battery, 505065, [Aliexpress](https://www.aliexpress.com/item/1005009908189503.html)                                         |
| **Battery Life**             | ~8 hours idle, 4-5 hours typical usage                                                                                                                 |
| **Battery Voltage Measurement** | ADC Technology, connected to pin PA0 of STM32H7        |
| **Magnet on Back Plate of NFC Board(Pogo pins)**     | [4x 4-Pin Pogo pin connector](https://www.lcsc.com/product-detail/C5126844.html) is a female version. For a breakout board you would need this [magnetic connector](https://www.lcsc.com/product-detail/C5126845.html?s_z=n_q_YZP0048-20048-04025-03&spm=wm.ssy.bg.0.xh&lcsc_vid=RwRWBFMFT1dZU1UCRVJcX11STgVXUVICQwBZVwYFRQAxVlNRQFNcVVRTRlhWUzsOAxUeFF5JWBYZEEoKFBINSQcJGk4eFQsCAgIaSgADAwAHC0slQlBcUVxSQ08GEwkK)  |
| **Audio components**               | [PCM5102APWR](https://www.lcsc.com/product-detail/C107671.html) as a DAC, [TPA6132A2RTER](https://www.lcsc.com/product-detail/C69901.html) as an AMP and a [PJ-327A 5JJ](https://www.lcsc.com/product-detail/C668605.html?s_z=n_q_PJ-327A%25205JJ&spm=wm.ssy.bg.0.xh&lcsc_vid=RgReVVxRRFgLUlFfQlJXAVEAFVhaX1EDT1YIBQVVQlYxVlNRQFNcVVZTRlFdUTsOAxUeFF5JWBYZEEoKFBINSQcJGk4eFQsCAgIaSgADAwAHC0slQVhXV1VIHxUDCw%3D%3D) as a jack 3.5mm connector for headphones.           |  
| **Dimensions**                      | 70x100x25mm(W, L, H) which I find pretty solid(Only the PCB Assembled size), but I assume with a casing it would be with casing around 74x104x29mm(W, L, H)|
---

## .IOC
<img width="1128" height="1137" alt="image" src="https://github.com/user-attachments/assets/dddf058d-e189-4629-8f53-ac9c78bdaf30" />

---


Questions or need more info? Reach out to me!\
Discord: **Sleepymorph**\
Telegram: **@ifyouask3d**

---

<h1 align="center"><b>Funded by:</b></h1>

<p align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="LOGO/flag-standalone-wtransparent.png">
  <source media="(prefers-color-scheme: light)" srcset="LOGO/flag-standalone-bw.png">
  <img alt="SAIL THE PROTOTYPE LOGO" src="URL_TO_BLACK_IMAGE">
</picture>
 </p>

 Thanks a lot to [Hack Club](https://hackclub.com/) for funding this project!
 
 The project got reviewed and approved by [CAN](https://github.com/claynicholson)
