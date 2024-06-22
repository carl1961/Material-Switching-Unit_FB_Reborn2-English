[![you can get this shield at shields.io](https://img.shields.io/discord/771052481538031637?color=7289da&logo=discord&logoColor=white)](https://discord.gg/TXhCJRbFFt)            ![GitHub](https://img.shields.io/github/license/PierreMasselot1/Material-Switching-Unit) [![YouTube Channel Subscribers](https://img.shields.io/youtube/channel/subscribers/UCF2tb5Hu6G_z-tB3_e_9U4A?style=social)](https://www.youtube.com/channel/UCF2tb5Hu6G_z-tB3_e_9U4A)   

Устройство замены филамента для печати различными пластиками и многоцветной печати.

Модификация для принтера **FlyingBear Reborn 2**.

Исходное оборудование и модификации:
* экструдер BIQU H2 V2S
* обдув модели 1x5015
* wi-fi модуль удален
* моторы X и Y перевернуты
* материнская плата MKS Robin Nano 3.2 (STM32F407VET6)
* драйвер шаговых двигателей - TMC 2209
* датчик BLTouch (выравнивание UBL по 12x12)
* парковка Z по концевым выключателям.
* парковка X по XMAX
* доступная область печати 320x320x350мм

Для установки MSU требуется:
  * еще один драйвер шагового двигателя
  * поменять подключение шаговых моторов (без этого перестает работать мотор Z2 во время печати)
    * E0 -> E2
    * E1 -> E0
    * E2 -> E1
  * сервопривод для MSU
  * сервопривод для резчика филамента, в случае его использования

Сервопривод подключается к контактам:
   * PC3
   * PC2
     
Можно подключить на другие, но возможна нестабильная работа - дрожжание, поворот на неверный угол.

# Material Switching Unit (MSU)

The Material Switching Unit is a multi-material upgrade for 3D printers based on the MMU2 that allows printing of up to 5 filaments while staying under 80$ and being compatible with most FDM 3D printers out there.

# Getting started

Clone the repository using the following command (you will need [git](https://git-scm.com/downloads) on your machine)

`git clone --recursive https://github.com/PierreMasselot1/Material-Switching-Unit.git
`

Once this is done you should now have access to the different parts required for this project. The Marlin folder contains the modified firmware that will allow you to control the MSU and the parts forlder contains all the 3D files that you will need.

have a look at the [build guide](https://github.com/PierreMasselot1/Material-Switching-Unit/blob/main/Build_guide_MSU.md) for further guidance on how to get the MSU up and running!

# Goals

* The MSU is currently still a prototype, improving reliability is currentlyy the main goal. The main focus being at the Slicer level ([here](https://github.com/PierreMasselot1/SuperSlicer) is the fork that I am working on) but also some improvements that can still be done to the actual device.

* Presets and profiles! Not having the tweak the MSU for hours will make the barrier to entry much lower

# Notes

The main barrier I have right now is time, juggling everything from uni and career to friends and sports does take quite a bit of time so if you see that this repo hasn't been updated in a while it's not because the project is dead ;) it's just that I haven't had the time to work on it. 
