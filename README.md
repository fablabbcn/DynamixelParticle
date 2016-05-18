# Dynamixel AX-12 Particle Library

This is a port of the amazing [Savage Electronics](http://savageelectronics.blogspot.com.es/2011/01/arduino-y-dynamixel-ax-12.html) Arduino library for controlling [Dynamixel AX-12](http://support.robotis.com/en/product/dynamixel/ax_series/dxl_ax_actuator.htm) servomotors with the [Particle Photon](https://www.particle.io/).

No external electronics are required since the TTL Half-Duplex support is archived on [software](https://docs.particle.io/reference/firmware/photon/#halfduplex-).

You can find the API documentation [here](http://austinlpalmer.com/Projects/Documentr/#/home).

## Wiring

Simply connect the Photon `RX` and `TX`together to the `Signal` pin of the Dynamixel motors.

## Example

```
#include <DynamixelParticleSerial.h>

void setup(){
 Dynamixel.beginHalf(1000000);
}

void loop(){
  Dynamixel.setEndless(1, OFF);
  Dynamixel.move(1,random(200,800));    delay(1000);
  Dynamixel.moveSpeed(1,random(200,800),random(200,800));
  delay(2000);
  Dynamixel.setEndless(1,ON);
  Dynamixel.turn(1,RIGTH,1000);
  delay(3000);
  Dynamixel.turn(1,LEFT,1000);
  delay(3000);
  Dynamixel.setEndless(1,OFF);
  Dynamixel.ledStatus(1,ON);
  Dynamixel.moveRW(1,512);
  delay(1000);
  Dynamixel.action();
  Dynamixel.ledStatus(1,OFF);
}
```

## License

Dynamixel Half Duplex USART Comunication
Copyright (c) 2011 Savage Electronics.
Created by Savage on 27/01/11.

Dynamixel Half Duplex USART Comunication for Particle
Copyright (c) 2016 Pral2a - Fab Lab Barcelona.
Particle Port by Pral2a on 18/05/16.

This library is free software; you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation; either version 2.1 of the License, or (at your option) any later version.

This library is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along with this library; if not, write to the Free Software Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1301  USA
