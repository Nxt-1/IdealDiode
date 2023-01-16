# IdealDiode

A small implementation around a TI LM74700 ideal diode controller.

Ideal diode controllers are an idealistic approximation of a diode one-way current blocking functionality. This is achieved by switching an N-channel MOSFET when conduction is desired and using the MOSFET's internal body diode to block current otherwise. The TI part monitors the input and output voltage and drives the transistor when current need to block (i.e. when V_IN > V_OUT).

By fully saturating the transitor's gate, the voltage drop source and drain is in the order of tens of milivolts instead of the typical 700mV for a silicon diode.

## Use Case

This project is designed to be used when charching multiple 36V nominal (42V max) lithium battery packs in parallel. Specifically batteries with separated charge port BMS, that are always energised. If no protection was implemented, connecting the batteries in parallel could cause the full battery current of a battery with a higher state of charge to flow through the other battery's chargeport. Using a regular diode would effectively lower the maximum charge voltage by the diode's voltage drop, thus decreasing the usable battery capacity. Hence the ideal diode circuit.

## Specifactions

The device is designed to withstand 42V nomimal and a charge current of 5A.