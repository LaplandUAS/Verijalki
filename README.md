# Verijälki
Verijälki demonstraattorilla tutkitaan drone teknologian soveltuvuutta koirien verijälkikoulutukseen.

## Tarvikkeet
* [DJI Mavic Pro](https://www.dji.com/fi/support/product/mavic)
* [Arduino Nano](https://store.arduino.cc/products/arduino-nano)
* 250ml ruisku
* 5-6V DC peristatti pumppu
* UART radiomoduulit
* [Moottoriohjain-piirilevy](https://github.com/LaplandUAS/Verijalki/tree/main/pcb)
* [3D-tulostetut osat](https://github.com/LaplandUAS/Verijalki/tree/main/cad)

## Mekaniikka
Demonstraattorin mekanikka on toteutettu droneen kiinnitettävällä nestemäisen painolastin annostelijalla. Tämä koostuu 250ml jousiladatusta ruiskusta (fig.1.0), jonka syöttöä ohjataan peristaattipumpulla (fig.1.1).
Ruisku pysyy paineistettuna kompressiojousen (fig.1.2) avulla, mikä estää pumppua vetämästä ilmaa painolastiin.
(Kuvio fig.1 tähän)

## Elektroniikka
Pumpun syöttöä ohjataan langattomasti [HC-12](https://www.allaboutcircuits.com/projects/understanding-and-implementing-the-hc-12-wireless-transceiver-module/) lähetin/vastaanotin moduulia hyödyntäen.
Lähettimen signaali dekoodataan sarjaliikenteestä Atmega168 mikrokontrolleripiirin (fig.2.0) avulla, mikä puolestaan ohjaa moottoria H-sillan avulla (fig 2.1). Lähettimen puolella on vastaava Atmega168 mikrokontrolleri Arduino Nanon muodossa (fig.2.2), joka
kääntää potentiometrin (fig.2.3) vastusarvon sarjaliikenteeksi HC-12 moduulille. Pumpun ohjauspiirin virta saadaan dronen lisälaite portista, jonka micro-usb liitin on kytketty vasstaavasti:
| Nasta  | Selite |
| ------------- |:-------------:|
| 1      | GND  |
| 2      | 5V   |
| 3      | 1.5V |
| 4      |?     |
| 5      |?     |

Vain nastat 1 & 2 ovat tarpeellisia pumpun ohjaimen toiminnalle.
> [!CAUTION]
> DJI Mavic Pro:n lisälaiteväylä ei noudata perinteisiä micro-usb käytänköjä, eikä tämän vuoksi ole kytketty näiden mukaisesti. 

(Kuvio fig.2 tähän)


-----
Lisenssi info & logot
