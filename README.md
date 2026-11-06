# RGB LED Color Fading (Arduino)

Fades a single RGB LED smoothly through the colors of the spectrum:
**Red → Green → Blue → Red**, repeating forever.

Made by Sir Anwar Siraj, DS and AI Robotics.

## Components
- Arduino Uno (or compatible board)
- 1 × RGB LED (common cathode)
- 3 × 220 Ω resistors
- Breadboard and jumper wires

## Wiring

| LED leg | Arduino pin |
|---|---|
| Red   | 9 (PWM) |
| Green | 10 (PWM) |
| Blue  | 11 (PWM) |
| Common (longest leg) | GND |

Put one 220 Ω resistor in series with each color leg.

> Use only PWM pins (marked `~`) so `analogWrite()` can fade smoothly.

## How it works
- `analogWrite(pin, value)` sends a PWM signal with a value from 0 (off) to 255 (full brightness).
- The sketch has 3 stages: Red → Green, Green → Blue, Blue → Red.
- In each stage one color fades out while the next fades in, in 255 steps of 20 ms.
- One full cycle takes about 15 seconds.

## Colors
Each channel has 256 levels, so an RGB LED can make 256 × 256 × 256 = **16,777,216** colors.
This sketch shows **765 shades** along the edge of the color wheel.

## How to use
1. Wire the circuit as shown above.
2. Open the code in the Arduino IDE.
3. Select your board and port, then click **Upload**.
4. Change `DELAY_TIME` to make the fade faster or slower.

## Files
- `RGB_LED_.txt`: the Arduino sketch
