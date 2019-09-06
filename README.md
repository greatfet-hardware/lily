# Lily
an RF power detecting GreatFET neighbor

Required KiCad dependency:

https://github.com/greatscottgadgets/gsg-kicad-lib

If you are using git, the preferred way to install gsg-kicad-lib is to use the
submodule:

```
git submodule init && git submodule update
```

## potential ICs
* LTC5507 100 kHz - 1 GHz
* HMC1120LP4E DC - 3.9 GHz
* MAX2016 LF - 2.5 GHz dual channel
* ADL5904 DC - 6 GHz
* AD8363 DC - 6 GHz
* HMC909LP4E DC - 5.8 GHz

## Pin usage

signal  | pin     | alt1  | alt2
--------|---------|-------|-----
VOUT    | J2.05   | J2.09 | J2.16
ENBL    | J1.03   | J1.04 | J1.05
RST     | GND     | J1.20 | J1.22
Q       |         | J2.17 | J2.18
Q bar   |         | J2.30 | J2.31

## Initial calibration data
Calibration data was taken by driving the RF input of Lily with a function generator creating a 10MHz sine wave at various amplitudes (VPP). The analog voltage output (VRMS) was measured with an oscilloscope and the ADC was used to convert VRMS into a digital measurement. Driving Lily with an input of VPP = 4V resulted in Lily drawing 4mA of supply current. The input should not exceed VPP = 5.62V in order to avoid damaging the board.

VPP     | VRMS    | ADC
--------|---------|-------
10mV    | 25mV    | 7
50mV    | 0.258V  | 84
0.1V    | 0.478V  | 155
0.2V    | 0.697V  | 227
0.3V    | 0.830V  | 267
0.5V    | 0.988V  | 317
1V      | 1.2V    | 386
2V      | 1.4V    | 454
3V      | 1.57V   | 494
4V      | 1.66V   | 524
