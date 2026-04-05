# Conveyor Belt with Product Sorter

PLC: Siemens S7-1500 (CPU 1511-1 PN)
Software: TIA Portal V21
Language: Ladder (LAD)

## Description
Conveyor belt control system programmed on Siemens S7-1500 PLC. Implements automatic start/stop interlock, product detection and sorting, product counting, and fault indication.

## Tag Table

Btn_Start — Bool — %I0.0 — Start pushbutton
Btn_Stop — Bool — %I0.1 — Stop pushbutton
Sensor_Product — Bool — %I0.2 — Product detection sensor
Sensor_Fail — Bool — %I0.3 — Fault detection sensor
Engine_Belt — Bool — %Q0.0 — Belt motor output
Sorter — Bool — %Q0.1 — Product sorter output
Fail_Light — Bool — %Q0.2 — Fault indicator light
Active_Belt — Bool — %M0.0 — Belt active internal flag
Product_Detected — Bool — %M0.1 — Product detected internal flag
Product_Counter — Int — %MW0 — Product count (max 100)

## Program Logic

Network 1 — Belt start/stop interlock
Network 2 — Belt motor control
Network 3 — Product detection and sorting
Network 4 — Product counter
Network 5 — Fault indicator

## System Operation
- Press Btn_Start to activate the belt — interlock keeps it running
- Sensor_Product detects products and activates the sorter
- Product_Counter counts up to 100 products, resets on stop
- Sensor_Fail stops the belt immediately and activates fault light
- Press Btn_Stop to deactivate belt and reset counter

## Software Required
- TIA Portal V17 or higher
- SIMATIC S7-PLCSIM V21 for simulation
