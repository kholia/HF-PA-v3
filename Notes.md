In general terms, the PCB industry considers an RF circuit board to be any high
frequency PCB that operates above 100MHz.

IRF510 - The device dissipates 43 watts so as long as the kit doesn't draw more
that about 3.5 amps max at 12 volts, it won't fail. At 5 watts and 50%
efficiency it won't draw more than 1 amp and  can handle full reflected SWR.

https://www.rapidonline.com/Catalogue/Search?Query=CDIL

LED Wemos D1 Mini - The built-in led is on pin D4, and it is inverted.

```
Z=Vcc2 / 2PO
In [7]: (22 * 22) / (2 * 5)
Out[7]: 48.4
```

```
[dhiru@zippy DS1054Z_screen_capture]$ python2 OscScreenGrabLAN.py png 192.168.1.16
Instrument ID: RIGOL TECHNOLOGIES,DS1054Z,DS1ZA203916662,00.04.04.SP3

Receiving screen capture...
Saved file: 'captures/DS1054Z_DS1ZA203916662_2021-09-21_18.23.17.png'
```

From the internet,

7805 -> Without an extra heatsink, you can burn off up to 2W. If you need more
current heatsinks are cheap and effective. Every 11 degrees Celsius cooler you
run your semiconductors, reliability doubles.

- Get the max die temperature from the regulator datasheet

- Get the Theta(j-a) number from the datasheet in degrees C per watt.

- Calculate the power dissipated by your device. Example: 9 volts in, 5 volts
  out at 1 amp would be 4 watts.

- Multiply the watts dissipated by Theta(j-a) to get the temperature rise.

- Add the temperature rise to the maximum ambient temperature the device will
  be exposed to.

- If the number computed in #5 is greater than the max die temperature, then
  you need to use a heatsink or some other way to actively
  cool the device.

- If you use a heatsink, you will use a slightly different set of calculations
  involving the regulator's Theta(j-c) (Not Theta(j-a).

For a 7805 it's 65 C/W junction to air.

This means that if the regulator produces 1 W of heat, the die will be 65
degrees C hotter than the ambient air.  The maximum operating temperature is
125 C. Pune temperature (inside the case) -> 70 c.

Can dissipate -> (125 - 70) / 65 -> 0.84 watts. P = VI. This allows around
100mA of current when input voltage is 14v.

Note: Try the `Small mark` option instead of the regular `Real drill` option in
KiCad.

LTspice notes:

- Download LTspice (Google "Download LTspice"). It's free.

- `~/Documents/LTspiceXVII/lib`

  Extract external components to this path.

- Extract the `contents` of `LTspiceXVII_2019Jan29.zip` (Google for this file) properly to `~/Documents/LTspiceXVII` path.
