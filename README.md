# TesLorean-Battery-Controller
Arduino code to control the Chevy Spark EV 2014 A123 battery module and and monitor the BMS

The TesLorean is fitted with a Chevy Spark EV 2014 battery pack containing modules made by A123.

The Pack has two sets of B+B- high voltage lines, one for charging (no pre-charge protection) and one for drive systems (pre-charge protected).  There are two data/control low voltage ports.  One port connects to the BMS and output battery cell status, balancing information, and temperatures.  The other port has a number of lines dedicated to activating (with 12v) high voltage contactors.

The TesLorean Battery Controller will accept instructions to activate the high voltage contactors, and will also monitor cell statuses and temperature.  The controller will send summary battery status information and warning messages should any individual cell go into over or under voltage.  The battery controller will disconnect the pack (open the contactors) if the pack voltage falls too low - risking long-term damage.


Main Files
=========
BatteryControlModule.ino  - listens to the Spark's A123 battery system and commands Spark battery module contactors
BCM Testing Wiring.pptx   - How my Battery Control Module is wired up to the Spark/A123 interfaces
CAN Notes.txt             - A123 CAN frames

Old Demo Code Pieces
====================
BatteryDisplay CSV.py   - Reads in a CSV dumped by SavvyCAN from the BMS (relay_command_2.ino) and displays using PyGame
relays_command_1.ino    - Simple serial port command of Arduino connected to relays driving 12v signals to the battery contactors
relays_command_2.ino    - Sends signals (12v) to the BMS to enable data transmissions (cell voltages and temps)
