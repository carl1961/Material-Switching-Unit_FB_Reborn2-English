[![you can get this shield at shields.io](https://img.shields.io/discord/771052481538031637?color=7289da&logo=discord&logoColor=white)](https://discord.gg/TXhCJRbFFt)            ![GitHub](https://img.shields.io/github/license/PierreMasselot1/Material-Switching-Unit) [![YouTube Channel Subscribers](https://img.shields.io/youtube/channel/subscribers/UCF2tb5Hu6G_z-tB3_e_9U4A?style=social)](https://www.youtube.com/channel/UCF2tb5Hu6G_z-tB3_e_9U4A)   

Filament replacement device for printing with various plastics and multi-color printing.

Modification for the printer **FlyingBear Reborn 2**.
A small guide and [overview](https://rozhkovets-home.ru/?p=464)

It can be discussed [here](https://t.me/+KcA09gXNElsxNDQy)

Initial condition of the equipment and modifications:
* BIQU H2 V2S extruder
* Blower model 1x5015
* Wi-Fi module removed
* Drivess X and Y are inverted
* Motherboard MKS Robin Nano 3.2 (STM32F407VET6)
* Display MKS mini 12864 V3.0
* Stepper motor driver - TMC 2209
* BLTouch sensor (UBL alignment 12x12)
* Parking Z by limit switches
* Print area  300x300x350mm 

In addition to [the list](https://github.com/rozhkovets/Material-Switching-Unit_FB_Reborn2/blob/main/Build_guide_MSU.md#parts-required) требуемого оборудования требуется:
  * another stepper motor driver
  * change the connection of the stepper motors (without this, the Z2 motor stops working during printing)
    * E0 -> E1
    * E1(Z2) -> E0
    * The stepper motor MSU is connected in E2. 
  * servo drive for the filament cutter, in case it is used
  * filament presence sensor (BTT SFS or similar) **(highly recommended)**

The servos are connected to the contacts:
   * PC3
   * PC2
   * It can be connected to others, but unstable operation is possible - flickering, turning at an incorrect angle..
____________________
1. Print the necessary [parts](https://github.com/rozhkovets/Material-Switching-Unit_FB_Reborn2/tree/main/parts/Reborn2) 
2. Gather
3. Connect the motors according to the table.

|  Motor  |  Origin port  |  MSU  |
| ------------- | ------------- | ------------- |
|  X  |  X-motor  | X-motor |
|  Y  |  Y-motor  | Y-motor |
|  Z1 | Z1-motor  | Z1-motor |
|  E  | E0-motor  | E1-motor |
|  Z2 | E1-motor  | E0-motor |
|  MSU E |   | E2-motor |

4. Compile the firmware with the necessary settings and install the firmware..
5. Be prepared for problems

**Frequent problems:**
  * The MSU motor cannot push the filament - Increase or decrease the pressure. A large current for the motor is not required. It would be better if the motor starts skipping steps when it gets stuck, rather than grinding the filament.
  * The filament gets stuck in the splitter when entering the ptfe tube - Deburr the entrance to the ptfe tube with a knife. Slightly twist or remove the tube from the splitter. Change the angle of cutting the filament.
  * The filament gets stuck when entering the fitting - Use another fitting. Change the angle of the filament cut.
  *The filament gets stuck in the BTT SFS filament motion sensor - Change the cutting angle of the filament. Change the angle of the filament entering the sensor channel. Ream the output channel from 2 to 3 mm, create a small chamfer at the entrance to the channel. Suffer.
  * The filament gets stuck at the entrance to the cutter - enlarge the hole with a drill. Shift the filament motion sensor sideways by inserting washers. (Shifting it by 1 mm was enough for me). Change the angle of the filament cutting. Change the angle of the filament entry.
  * The filament is not being cut by the cutter - Replace the blade. Increase the number of cutting attempts.
  * The filament gets stuck at the entrance of the extruder - Change the filament cutting angle. Upgrade your biqu h2 v2 by installing a ptfe tube between the gears to reduce gaps, [instructions](https://m.youtube.com/watch?v=L_tcQAx7UfE).
____________________

# Material Switching Unit (MSU)

The Material Switching Unit is a multi-material upgrade for 3D printers based on the MMU2 that allows printing of up to 5 filaments while staying under 80$ and being compatible with most FDM 3D printers out there.

# Getting started

Once this is done you should now have access to the different parts required for this project. The Marlin folder contains the modified firmware that will allow you to control the MSU and the parts forlder contains all the 3D files that you will need.

have a look at the [build guide](https://github.com/PierreMasselot1/Material-Switching-Unit/blob/main/Build_guide_MSU.md) for further guidance on how to get the MSU up and running!

# Goals

* The MSU is currently still a prototype, improving reliability is currentlyy the main goal. The main focus being at the Slicer level ([here](https://github.com/PierreMasselot1/SuperSlicer) is the fork that I am working on) but also some improvements that can still be done to the actual device.

* Presets and profiles! Not having the tweak the MSU for hours will make the barrier to entry much lower

# Notes

The main barrier I have right now is time, juggling everything from uni and career to friends and sports does take quite a bit of time so if you see that this repo hasn't been updated in a while it's not because the project is dead ;) it's just that I haven't had the time to work on it. 
