# Keithley 2000: replacing the VFD with a 5.5 inch OLED

# 1.	Abstract
 
![image](https://user-images.githubusercontent.com/125270643/220696451-1b9ca844-73d5-4efc-ab0f-c9339e492362.png)

The aim of this conversion guide is to modify a DMM Keithley 2000 from the original display (VFD) to a 5.5 inch OLED.

The 5.5 inch OLEDs are currently available in the color variants yellow or green only. The displays available in US and Europe are of equivalent quality to those available from china, it can be assumed that they all come from the same source anyway. Depending on the color requirements, costs and demands on the delivery time (and by not thinking about the possible customs fees for foreign deliveries), you can freely select your OLED display as long as it complies with the specification below.

The new and function compatible PCB fits into the front of a Keithley 2000 without any changes. A μController evaluates the serial protocol for the measurement presentation on the OLED and also generates the codes when the keys are pressed.

The appearance on the OLED is intentionally based on the original display, here a completely different presentation of the measured values and the status display (annunciators) would be possible. But the familiar view should remain, only bigger and easier to read it should be.

In the upper levels of the display and menu, many textual optimizations have been made in the software. With the graphic display, unlike a VFD, the display of upper and lower case letters as well as symbols are possible.

Two converted devices are in daily use for over a year now. The current software version is stable but may not be error-free, such a development is actually is never completed and can be further optimized until the eternity. 



# 2. Electrical

The PCB V1.1 must be assembled in accordance with the Component Placement and the Bill of Material.Since the PCB V1.1 has not yet been manufactured, only photos of the PCB version 1.0 are available here, but the differences are only marginal.


![image](https://user-images.githubusercontent.com/125270643/220697192-49861e83-101c-4e57-b2c9-8cff3d52f6b2.png)

![image](https://user-images.githubusercontent.com/125270643/220697241-d525f35f-c24e-4359-8db8-d4794934c4cf.png)

Basically, OLEDs of any size can be used here as long as the resolution, the controller and the interface match. However, the mechanical part of this description is aimed at the use of a 5.5 inch OLED.

The OLED must be used in the "panel" version (glass only). There are also "modules" with integrated electronics, you could use the OLED glass, if you take the module apart. The display must meet the following specifications:

•	Resolution 256 x 64 dots

•	Controller SSD1322

•	8-bit parallel interface (additional serial interface is not used here)

•	Dimensions 146 x 45 x 2 mm (5.5 inch, W x H x D)

•	FPC connector 30 pins, 0.5 mm pitch

The following OLEDs were successfully tested:
1.	EA W256064-XGLG (yellow), Display Visions
2.	Green 5.5 inch Graphic OLED Display Panel 256x64 SSD1322 Parallel/SPI, BuyDisplay
3.	White/Yellow/Green/Blue 3.12 (also named 3.2) inch OLED Display Panel 256x64 SSD1322 Parallel/SPI, BuyDisplay

In the final position of the OLED, its connection cable is too short and must be extended with the help of an intermediate adapter. There are FPC cables in different numbers of poles, pitch and lengths available, here an approx. 10 cm long piece of FPC cable 30-pole with 0.5mm pitch is suitable. Also there are the ready-assembled adapter circuit boards available, sometimes in combination with the cable.


![image](https://user-images.githubusercontent.com/125270643/220697429-5741505b-da4d-4e01-8c30-598813d142ef.png)
![image](https://user-images.githubusercontent.com/125270643/220697478-bd879277-a5b9-4432-855d-ee1ddc9a41f4.png)

ATTENTION:

There are basically two types of FPC connectors: one with the contacts at the top and the other version has the contacts at the bottom – this determines whether you have to insert the FPC cable with the contact surfaces up or down. With an adapter this doesn't matter, you just have to plug in the FPC in the right way to get contact. With this PCB you HAVE to use the version with the contacts at the top, otherwise the connections will be mirrored and a plugged in OLED would probably be destroyed. The FPC cables are available in different versions with the contact surfaces on the same or on different sides, this leads to a contact mirroring also. In summary you must know what you are doing here to get it right.

Finally, a 16-pole ribbon cable, length approx. 200mm, with a 16-pin socket plug on both sides must be produced. The cable connects the new display board to the main board. The socket plugs must be pressed in such a way that a pole-correct connection can be established (connection pin 1 to pin 1). If the ribbon cable is made and folded as shown in the picture, this fits exactly into the device.


![image](https://user-images.githubusercontent.com/125270643/220697590-e16ea9ee-55e0-420f-98d1-17a1139c80f1.png)

After completion of the printed circuit board, it should be electrically tested and then the μController programmed via the ST-Link interface. You need to have an appropriate programmer (ST-Link V2) and the ST-Link-Utility-Software to do so.

Note: The jumper JP1 should not be set. Here the character set can be switched to a 14-segment emulation. It just was an experiment and it looks even worse than the original.
 
 
 
# 3. Mechanical

The mechanical difference between the original VFD and the OLED is the position of the display. It can no longer be placed on the front board PCB but has to be positioned as close as possible to the acrylic display cover. Further the 5.5 inch OLED glass display does not fit into the existing space. Therefore some mechanical work has to be done. 

The front element of the Keithley-2000 housing must be completely detached from the device and the original Front Circuit Board with the VFD and the rubber keyboard mat must be removed.

To operate with an OLED, the acrylic display cover must be replaced. The original acrylic glass has a light transmission of about 40%, which is suitable for increasing the contrast of a VFD, but is not suitable for an OLED, which already offers a high contrast but does not have such high brightness.

The new display cover should be made of clear acrylic glass measuring 162mm x 42mm, with a thickness of 3.0mm (2.5mm would be ideal, but that's hardly available). In the manufacturing process, the cut edges should be polished. But be careful: acrylic glass processed in this way reacts sensitively to IPA, which can lead to disturbingly visible microcracks on the edges.

In order to get the original acrylic glass out, some violence is required. The acrylic glass is attached to all support areas with double-sided adhesive tape. The use of hot air is not recommended, plastic parts are deformed too quickly, which can lead to irreparable damage. So you have to carefully try with heavy thumb pressure from the inside to the outside to first find a place where the bonding dissolves, then continue working from there without damaging the plastic front. Once the original glass has been taken out, all adhesive residues must be removed from the front.


![image](https://user-images.githubusercontent.com/125270643/220699712-ef51d4bd-9ab1-40ff-a688-778b3223a1aa.png)

Next, the mechanical processing of the front of the device should be carried out. This is to take care that the 5.5 inch OLED will fit in. Here a few millimeters are missing in height. These are obtained by taking away some material from the guides of the rubber key mat, just enough that the inner guidance remains undamaged. Not only the space for the glass of the OLED must be created, but also for the FPC connection cable, this must not be bent too much and not too close to the glass. In addition, the OLED should be able to rest flat from behind on the front of the device, therefore the part of a frame must also be milled away. Later, the OLED will sit at a distance of about 1mm from the acrylic glas.

To carry out the upcoming milling work, the front of the device must be fixed in the working area of the CNC milling machine in such a way that the contact surface of the OLED glass corresponds to the working plane of the milling machine. The support of the OLED must be positioned exactly at right angles to the Z-axis also. Then you can use almost any milling insert (3-6mm are useful) and a hand-operated process of the spindle to move the interfering plastic parts back and forth several times and gradually remove the feed of the Z-axis. Due to the brittle key guides, it is advisable to move all axes only with a low feed. 

At the end of the work, the OLED should be able to be inserted easily and without applying any force flat into it’s position. The rest of the milled bridge ensures a hold in a horizontal position.


![image](https://user-images.githubusercontent.com/125270643/220699917-18ecade2-62ae-44f5-a596-cda6e06741bd.png)

![image](https://user-images.githubusercontent.com/125270643/220700017-e8aea54e-d70d-4038-81b2-72896c96a0d6.png)

![image](https://user-images.githubusercontent.com/125270643/220700099-4ead2e27-852b-4bbc-b664-4e11c40b071e.png)

The front processed in this way does not result in any optical or functional losses on the device. Even the original front PCB can be reinstalled and operated (together with the original acrylic glass).
 
Since the original acrylic glass is replaced by a transparent one, all surfaces and edges visible through the screen should be blackened, because they are now visible through the clear acrylic. For this purpose, matt black lacquer, sprayed (using masking tape) or applied with a brush is suitable.


![image](https://user-images.githubusercontent.com/125270643/220700189-bb8b39d0-4277-4d15-8783-4e3fba27d3e0.png)

![image](https://user-images.githubusercontent.com/125270643/220700224-ea18bba2-dc3d-4c82-8447-a84a81d47836.png)

If you now insert the 5.5 inch OLED in the newly created space, it should look like this:

![image](https://user-images.githubusercontent.com/125270643/220700309-dbdbaed7-d807-4a1a-a547-64bb685c5754.png)
 
The new acrylic glass pane must now have a back blackening. Here at least the adhesive areas and all edges which can be seen through the acrylic glass should be covered.


![image](https://user-images.githubusercontent.com/125270643/220700398-af9daf6d-76b8-4e22-8f3e-3f448650fd33.png)

This is best done after masking with matt black spray paint. After the drying process, the glass can be glued into the front of the device with very thin transparent double-sided adhesive tape (3M mobile phone mounting tape). For this purpose, the adhesive tape is applied over the entire surface to the contact surfaces of the front of the device and any existing protrusions are separated.

The acrylic glass can now be brought into place and pressed tightly, it looks like this:


 ![image](https://user-images.githubusercontent.com/125270643/220700817-cb027c07-8b77-4e85-a569-ba51168785b7.png)

Since the original FPC cable of the OLED is too short, an extension is used. The small connector PCB is fixed to the back of the OLED and contacted with the display and extension.


![image](https://user-images.githubusercontent.com/125270643/220700906-560225b2-ef89-4b8f-bb8b-caa13c7595c3.png)

The key mat can then be reinserted. To keep the OLED in its position, two electrically non-conductive foam rubber pieces are glued to the front of the new front PCB – the exact position is not important, only they should not come into the area of the adapter PCB and the FPC line. The foam rubber pieces should have a sufficient thickness so that the OLED is pressed well to the front of the device.


![image](https://user-images.githubusercontent.com/125270643/220701009-bfb20687-6ae0-4c41-ba70-72eb45b89519.png)

ATTENTION:

The following photos show the assembled PCB version 1.0.

After that, the new circuit board can be installed in the front of the device. The FPC line is guided through the upper of the two slots (in the V1.0 layout – in version V1.1 there is only one slot). It should be noted here that the FPC line is exposed and cannot come into the action range of the keys. So pull the FPC line as far as possible and let the loop run on the back.

 
![image](https://user-images.githubusercontent.com/125270643/220701112-3b64c7c3-5902-4f71-a61f-87ec5d59ff8e.png)

Finally, the FPC cable can be plugged into the connector on the new front PCB and the retaining bracket pressed on.


![image](https://user-images.githubusercontent.com/125270643/220701197-196abcfd-b43f-49f3-9855-e51f06cc3403.png)

This completes the conversion and the Keithley 2000 can be reassembled except for the housing and finally powered on. With an existing electrical connection between the front and the main board, the μController can now be programmed. After a power cycle the device should be fully functional. The firmware is about 4 times faster than the speed of Keithley display actualization.

Note:

The jumper JP1 should not be plugged on. This is to switch to a 14-segment emulation of the display. It used to be an experiment, but it looks even more disgusting than the original.
 
