# TEA5767 FM Radio Receiver Module
## Created by: Darren Prong at Humber College Technical Laboratories
## CENG 317 Instructor: Kristian Medri

## Table of Contents
1. [Introduction](#introduction)

2. [Specifications](#specifications)

3. [Design Files](#design-files)

4. [Assembly](#assembly)

5. [Test Code](#test-code)

### Introduction
![Image of Prototype](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/CurrentSetup.jpg)

This list will allow you to complete a working FM Radio Receiver using the Raspberry PI 3b+ in conjunction with a TEA5767 I2C device.

Ill start by listing the required components, where to buy them, how to design then assemble those components, then finalize with testing the device in an appropriate enviroment.

This project was completed over a 15-week semester, however with these steps, a working prototype could be completed in a week from purchasing components to hearing music on the receiver.

### Specifications
Heres a list of all parts needed to complete this project.

![Image of Parts](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/PartsList_Updated.PNG)

Youre budget will vary from mine, as I had a number of components and tools and access to a prototyping lab which greatly decreased my overhead costs. 
I also had to buy additional components that were not originally on the budget or parts list files that I have uploaded HERE on my repository.
As well, my major mistake of frying a Raspberry PI (which could set you back another $50.00) wasn't included in the budget.
The amplifier originally was planned to be the Class-D amp supplied by buyapi.ca, however I had to put togther the LM386 due to time contraints. However, looking back, this would be a better option; thats why I left it on the final parts list.
My total budget by the end of the project was $122.68CAD.
I had intitially proposed a $108 total budget.

![Image of Budget](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/budget.png)

Here is the updated budget
These are the costs to be expected, at least at a minimum.

![Image of Invoice1](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/tea5767_invoice.png)

![Image of Invoice2](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/invoice_raspberry_amp.png)

![Image of ](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/)

Again, these prices are location dependent, as your geographical situation could greatly increase shipping costs or parts availablity. 
As well, in our prototyping lab, we have access to a $20,000 laser cutter, a lot of spare components and tools, the expertise of professionals, and a great deal more time.

### Design Files
Designing this next two major parts will require some trial and error if you haven't used these programs before. Also, if you've ordered your parts and awaiting the sensor in the mail, this can be done in the interim.
To design the device PCB I used the freeware "Fritzing" (which is in BETA at the time of this publication.) 

![Image of Fritzing](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/TEA5767_fritz_pcb.png)

This files could still use some tweaking, and maybe some personal customization; however, this is the simplest design I could create and good for a beginner to learn the basics.

And for the enclosure, CorelDRAW was used on a free 15-day trial as well as access to the program in our lab.
The enclosure on CorelDRAW:

![Image of Enclosure](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/Final_Enclosure_TEA5767.jpg)

After these are designed, you can send the fritzing file away to be printed.
The enclosure was printed a few times, with minor changes for each new job. Its still not a perfect fit, but the file you have here [Enclosure](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/Final_Enclosure_TEA5767.cdr) will work but the fit is tight, and the middle plate is under pressure from the USB ports pressing from underneath causing it to bend slightly. 


### Assembly
Once the parts are in hand, the design files printed and assembled, Heres what you should have in hand:
...

Start by attaching the the sensor to the PCB, I used hotglue.

![Image of TEA5767](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/PCB_TEA5767.jpg)

Next step will be to solder a jumper wire from each terminal on the sensor to the corresponding trace on the PCB.

![Image of Connection](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/FirstConnections_toplayer.jpg)

![Image of Jumpers](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/TEA5767_soldered)

Next will be to solder the via's. I recommend that you take a small amount of 20gauge wire(1cm in length) strip only one end and then insert into all the via's. This will hold it inside the via briefly while you solder the flip side. Solder the entire side with exposed wire first, then flip, remove the insulation, and solder that side for each via.

Double check the shape of each via and how the solder "flows" from the wire onto the copper pad. This ensures a solid connection. It should appear like a sloping hill, or a "Hershey Kiss".

Next, the 40-pin stackable header, along with the two screw terminals to be used with your speakers.

![Image of Bottom](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/BottomLayer.jpg)

![Image of Top](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/TEA5767_soldered.jpg)

Soldering all 40pins isn't necessary, I only soldered the pins I was using, and two on the far end of the header.

I also left my male 40-pin header plugged in, so I didnt lose it. However, you'll notice it doesn't rest flush up agaisnt the the female header. This could potentially damage both headers as well as the device. 

Best practice would be to disconnect from the PI each time your completed testing. 

You can now solder on a length of wire (up to you how long) to act as the antenna. Solder this in a similar way as you did with the via's.

![Image of PI](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/PI_tea5767_PCB.JPG)

PS. Ignore the jumper wire from the ground trace to pin 5. This was where I made a critical error in my fritzing design.
The updated .fzz has fixed this issue.

 Next and final step for assembly, attach your PI to the base plate of the acryllic enclosure with the ordered hardware and printed standoffs. 
 
 ![Image of Hardware](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/PI_Hardware.JPG)
 
 Do one hole at a time. Keep the device firmly planted on a flat surface. (hang over on hole on the edge of a table for example) place the standoffs in between the board and the base plate. Line up the holes, and insert a screw. While keeping the screw in place with your small philips head screw driver, place a nut on the threads with the needle nose pliers. The pliers are to be help still, just keep the nut from turning. Use the screwdriver to tighten, just until enough threads are engaged to hold the screw in place. Repeat for all four holes. Final step is to tighten down snugly, not firmly, on all four screws.
 
You can now attach all parts of the enclosure to the base, and plug in the PCB/device combo into the GPIO pins.

The final product:

![Image of Case](https://raw.githubusercontent.com/DarrenProng/Hardware-Production/master/images/PI_IOPanel.JPG)

### Test Code

The first step in making sure your PI will be able to play music will be its ability to first boot up, then to enable I2C devices, then to detect that the PI can recognize the sensor.
