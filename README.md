[![you can get this shield at shields.io](https://img.shields.io/discord/771052481538031637?color=7289da&logo=discord&logoColor=white)](https://discord.gg/TXhCJRbFFt)            ![GitHub](https://img.shields.io/github/license/PierreMasselot1/Material-Switching-Unit) [![YouTube Channel Subscribers](https://img.shields.io/youtube/channel/subscribers/UCF2tb5Hu6G_z-tB3_e_9U4A?style=social)](https://www.youtube.com/channel/UCF2tb5Hu6G_z-tB3_e_9U4A)   

Устройство замены филамента для печати различными пластиками и многоцветной печати.

Модификация для принтера **FlyingBear Reborn 2**.
небольшой гайд и [обзор](https://rozhkovets-home.ru/?p=464)

обсудить можно [здесь](https://t.me/+KcA09gXNElsxNDQy)

Исходное состояние оборудования и модификации:
* экструдер BIQU H2 V2S
* обдув модели 1x5015
* wi-fi модуль удален
* моторы X и Y перевернуты
* материнская плата MKS Robin Nano 3.2 (STM32F407VET6)
* дисплей MKS mini 12864 V3.0
* драйвер шаговых двигателей - TMC 2209
* датчик BLTouch (выравнивание UBL по 12x12)
* парковка Z по концевым выключателям
* доступная область печати ~300x300x350мм 

В дополнение к [списку](https://github.com/rozhkovets/Material-Switching-Unit_FB_Reborn2/blob/main/Build_guide_MSU.md#parts-required) требуемого оборудования требуется:
  * еще один драйвер шагового двигателя
  * поменять подключение шаговых двигателей (без этого перестает работать мотор Z2 во время печати)
    * E0 -> E1
    * E1(Z2) -> E0
    * шаговый двигатель MSU подключается в E2  
  * сервопривод для резчика филамента, в случае его использования
  * датчик наличия движения филамента(BTT SFS или им подобные) **(крайне рекомендуется)**

Сервоприводы подключаются к контактам:
   * PC3
   * PC2
   * Можно подключить на другие, но возможна нестабильная работа - дрожжание, поворот на неверный угол.
____________________
1. Распечатейте необходимые [детали](https://github.com/rozhkovets/Material-Switching-Unit_FB_Reborn2/tree/main/parts/Reborn2) 
2. Соберите
3. Подключите моторы в соответствии с таблицей

| Motor | Origin port | MSU |
| ------------- | ------------- | ------------- |
| X | X-motor  | X-motor |
| Y | Y-motor  | Y-motor |
| Z1 | Z1-motor  | Z1-motor |
| E | E0-motor  | E1-motor |
| Z2 | E1-motor  | E0-motor |
| MSU E |   | E2-motor |

4. Скомпилируйте прошивку с необходимыми настройками и установите прошивку.
5. Будьте готовы к проблемам

**Частые проблемы:**
  * Мотор MSU не может протолкнуть филамент - Увеличьте или уменьшите прижим. Большой ток для мотора не требуется. Будет лучше, если при застревании мотор начнет пропускать шаги, а не грызть филамент.
  * Филамент застревает в сплиттере при входе в ptfe-трубку - Развальцуйте ножом вход в ptfe-трубку. Слегка выкрутить или извлеките трубку из сплиттера. Измените угол резки филамента.
  * Филамент застревает при входе в фиттинг - Используйте другой фитинг. Измените угол резки филамента.
  * Филамент застревает в датчике движения филамента BTT SFS - Изменить угол резки филамента. Изменить угол входа филамента в канал датчика. Рассверлить выходной канал с 2 до 3 мм, сделать небольшую фаску на входке в канал. Страдать.
  * Филамент застревает при входе в резак - Расширьте отверстие сверлом. Сдвинте в сторону датчик движения филамента, подложив шайбы. (Мне было достаточно сдвинуть на 1 мм). Измените угол резки филамента. Изменить угол входа филамента.
  * Филамент не отрезается резчиком - Замените лезвие. Увеличьте количество попыток резки.
  * Филамент застревает при входе экструдер - Измените угол резки филамента. Модернизируйте свой biqu h2 v2 установив ptfe-трубку между шестерянми, чтобы уменьшить зазоры, [инструкция](https://m.youtube.com/watch?v=L_tcQAx7UfE).
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
