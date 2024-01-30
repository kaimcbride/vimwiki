# ABOUT LIFEPO4


Can be discharged regularly down to 20% (vs 50% for Lead Acid)

Higher charge rating. 0.5C recommended. Example 100Ah battery charged with 50Amps in 2hrs

Discharge 100% down to 20%: 2,500 cycles. 100% to 30% 3000 cycles. 100% to 50% 5000 cycles

Around 92% Efficient

Like being in the 20% to 85% charge range

## CHARGING

*Bulk Stage:* Constant Current applied until battery reaches Absorption Value Voltage

*Absorption:* Constant Voltage applied for 2hrs of Absorption: Voltage held steady and the current will start going down. 

*Float:* After 2hrs of Absorption, battery goes into Float state. Charge Controller Turns off. 

## ABSORPTION PHASE AND TAIL CURRENT

Lithium Doesn't need the Absorption Phase! When the charge reaches 28.4 can be considered fully charged (check this against my battery). 
Synchronization of the battery monitor can thus be at the end of the Bulk Phase. 
Take the Absorption voltage minus 0.2 V and a Tail Current of 5% for 5 minutes. Battery can be considered full. 

Tail Current: Wait for the battery to go into Float. Wait 10 minutes and see how much current is flowing into the battery. That is the Tail Current. Set tail current on the BMV to slightly higher than this value.

## LOW VOLTAGE DISCONNECT 

Discharge floor sent to 10 to 15% on the BMV Monitor

## LOW TEMPERATURE

Battery must not be charged below 32F. Discharge okay.


## OFF GRID GARAGE RECOMMENDATIONS
[MPPT SETTINGS VIDEO](https://www.youtube.com/watch?v=xBu7ScAdKrg)
He recommends these values:
- Absorption: 3.45V per cell, 8 cells in our battery, so 27.6V
- Float: 3.35 per cell, 26.8V
- EXPERT:
    - Tail Current: 1.0A
    - Absorption Time: 2.0hrs
    - Re-bulk: 1.0V (I might want to change this value)
