# IR-based system for measuring the thickness of cell layers
# Authors 
- Marta Luterek
- Aleksandra Rzeczyc
# Description of the project 
The purpose of the project was to create a simple device capable of measuring changes in infrared (IR) light intensity. The device uses an IR emitter diode, a phototransistor coupled with resistors, and Raspberry Pi to display the results. Such measurements can be used for multiple purposes, with the original idea behind the project being to approximate the thickness of the layer of cells in cell culture. The idea behind the applications of this device was that can be applied to mammalian cell culture, specifically to tumor cells or tissue culture. Since tumor cells are characterised by uninhibited growth, they grow in multiple layers or to tissue culture and the approximate thickness of the cell layer can approximate the number of layers and therefore the age of the cell culture.

# Science and tech used 
Light is emitted by an IR emitter diode, which then can pass through a sample, after which it gets received by a phototransistor. This ensures detection of changes in continuous IR intensity over time. The phototransistor is connected to a set of three 10kΩ resistors connected in a series, which enable the signal to be amplified before reaching the ADC. The resistor value was adjusted experimentally to maximize sensitivity while maintaining a reasonable signal-to-noise ratio. The analog output of the IR sensor is connected to an analog-to-digital converter (ADC), which is then connected to one of Raspberry Pi Zero W’s analog input pins. The results were read and displayed using a simple Python script provided with the Adafruit Circuit Python ADS1x15 library.

* [Raspberry Pi Zero W](https://botland.com.pl/moduly-i-zestawy-raspberry-pi-zero/8741-zestaw-raspberry-pi-zero-w-basic-5903351240109.html)

* [ADC 16-bit converter - 4-channel ADS1115 - overlay for Raspberry Pi](https://botland.com.pl/raspberry-pi-hat-ekspandery-wyprowadzen/9861-przetwornik-adc-16-bitowy-4-kanalowy-ads1115-nakladka-dla-raspberry-pi-5904422314460.html)

* [Phototransistor SFH-313FA 5mm 870nm](https://botland.com.pl/fototranzystory/4245-fototranzystor-sfh-313fa-5mm-870nm-5-szt-5903351245760.html)

* [JustPi THT CF carbon resistor 1/4W 10kΩ](https://botland.store/through-hole-resistors-tht/20150-justpi-tht-cf-carbon-resistor-14w-10k-30pcs-5904422329280.html)

* [IR 940nm transmitter + wire - Iduino SE028](https://botland.store/led-ir-infrared/14286-ir-940nm-transmitter-wire-iduino-se028-5903351242011.html)
* Breadboard and cables
* Prusa 3D printer and PLA filament

# State of the art 
The electronic circuit was successfully connected and tested. The baseline readings were estimated to be over 5900 (arbitrary units). When the emitter diode was positioned around 1 cm away from the detector, the read-out values were at least 5 times higher (over 25000). This confirms that the IR signal was being detected.

Work on the project carried out during the Garage of Complexity classes also included using an IR detector diode, however this was unsuccessful due to the diode detector being primarily designed for detecting the presence or absence of modulated IR signals (the obtained result is binary). Therefore, this type of detector was not suitable for measuring changes in the continuous intensity of IR light, which was the aim of the project. Furthermore, originally an optical fiber was also tested as a means to emit the IR light, but this was found to not provide strong enough light signal. A case to support the sample and enclose the electronic circuit was designed in Tinkercad and 3D printed on the Prusa printer. However, this case was designed for the IR diode detector before the mistake of using it for this purpose was spotted and the case hasn’t been re-printed due to time constraints. Designs and photos of the printed case were nonetheless included in this project description files.

# What next?
In order to use the device in its intended application to measure the thickness of cell layers, tests using various liquids would be required to see how the signal output values change with different liquids (e.g. water, cell medium, cell medium with cells), characterised by different densities, absorption coefficients and other relevant physicochemical properties. Ultimately, a calibration curve using cell cultures of various number of layers would be performed to establish a mathematical equation describing the relationship between IR intensity changes and the number of cell layers. Perhaps these tests would also reveal a need to fine-tune the electronic circuit itself, such as testing more resistor values and ways to connect them.
# Sources 
- [Writing on GitHub] ( https://docs.github.com/en/get-started/writing-on-github )
- [Phototransistor and Arduino] ( https://botland.store/content/157-Phototransistor-and-Arduino )
