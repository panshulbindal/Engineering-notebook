# ADC (Analog to Digital Converter)

## Definition 
An ADC is an electronic circuit or device that converts continuous analog signals(Continuously variable signals) into discrete digital binary numbers(1s and 0s).

## Types of ADC
- Successive Approximation Register (SAR): Uses an internal binary search to balance speed and circuit complexity; standard in general-purpose microcontrollers.
- Flash ADC: Compares voltages simultaneously using a large bank of comparators; extremely fast but power-heavy and limited in resolution.
- Sigma-Delta ADC: Oversamples the signal with noise shaping; slow conversion time but yields very high resolution (16 to 24 bits), ideal for audio and precise measurements.
- Dual-Slope (Integrating) ADC: Integrates the input voltage over a set time period; slow, highly noise-resistant, common in digital multimeters.

## Importance 
 The physical world is analog. Microcontrollers are digital computers that cannot process continuous voltages from sensors without translating the voltage. Therefore an ADC is acts as a translator and plays a vital role in bridging the physical world with digital world. Without it, computer will a CPU will never be able to understand physical inputs. 

 ## ADC on ESP32
 The ESP32 features two 12-bit Analog-to-Digital Converter (ADC) units—ADC1 and ADC2—supporting 18 total channels, but it suffers from non-linearity and high internal noise. Readings map 0V to 3.3V into digital values from 0 to 4095, though reliable measurements require proper attenuation and software filtering.
 - ADC1 (GPIO 32–39): 8 channels, completely independent and safe to use alongside Wi-Fi.
 - ADC2 (GPIO 0, 2, 4, 12–15, 25–27): 10 channels that cannot be used when Wi-Fi or Bluetooth is active. Several pins also double as strapping pins.
 - Non-Linearity: The output is non-linear; it clips near 0V and 3.3V. The safest linear measuring range is roughly 0.15V to 2.45V.

 Attenuation Ranges - 
 - 0 dB: Range up to ~800 mV (ADC_0db)
 - 2.5 dB: Range up to ~1100 mV (ADC_2_5db)
 - 6 dB: Range up to ~1350 mV (ADC_6db)
 - 11 dB: Range up to ~2600 mV / 3.3V (ADC_11db)