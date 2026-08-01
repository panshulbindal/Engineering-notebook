# GPIO (General Purpose Input/Output)

## Definition 
They are programmable pins on a microcontroller such as arduino uno or esp32, that can be configured by a software to either read digital signals (Input) or send digital signals(Output)

## Importance 
They help microcontrollers interact with the real world
- Read a button
- Blink an LED 
- Control a relay
- Read a motion sensor
- Send a digital signal to an actuator

## GPIO on esp32
- configurable through software 
- supports digital input and output
- Some pins also support PWM, ADC, and communication protocols such as SPI, I2C and UART.
- Pins - (1) 3.3V voltage regulator
         (2) GND ground reference pins
         (3) VIN or 5V input pin for external 5V power
  Analog pins - ADC 1 - 8 channels - 32-39
                ADC 2 - 10 channels - 0,2,3,12-15,25-27 (cannot be used as analog inputs if Wi-Fi is actively turned on)
                DAC - 2 channels - 25-26 (These act as true analog outputs, allowing us to generate actual variable voltages or audio signals)
  Capacitive pins - 10 pins - internal touch sensors can detect human skin contact - 0,2,4,12,13,14,15,27,32,33
  PWM pins - All 21 output capable GPIO pins can generate PWM signals
  Safe to use (I/O): GPIO 16-19,21-23,25-27,32,33
  Input only: GPIO 34-36(VP), 39(VN) - use external resistors if wired to a switch
  Boot-strapping pins: GPIO 0,2,5,12,15
  Not for use(Internal flash 4MB): GPIO, 6,7,8,9,10,11