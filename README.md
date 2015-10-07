Return Home (RTH) for OpenPilot CC and CC3D Boards 
==================================================

The files contained in this repository restore RTH, or more correctly turn to home (TTH), for the CC & CC3D boards.

OpenPilot support for the CC and CC3D boards and variants ceased with OpenPilot-RELEASE-15.02.02. The source repositories for this revision were available on the OpenPilot site at the time of writing (18 Sept 2015).

Support for return to home (RTH) and navigation generally for these boards was displaced by other functionality directed principally at multicopters some time ago. This occured well prior to the 15.02.02 release. It has been widely stated, incorrectly, that RTH was no longer possible within the available space on the ArmF321xx processor.

The solution adopted here is to use the GPS course made good to calculate either a roll or yaw correction for fixed wing aircraft. These corrections are then fed directly to the attitude control routines bypassing the original path planning and execution schemes. 

Muticopters may adopt the simple expedient of pitching forward, thus establishing a course over ground, then use yaw correction. 

Altitude hold may be added trivially for most sedate powered gliders and the stubs for this are also given. The assumption however is that the aircraft is still visible but orientation has been lost and that altitude is being managed by the pilot.

See OpenPilotSetup in wiki.

These files are provided under the GNU Public License (GPL) Version 3 and are for information and use by those who accept ANY AND ALL ASSOCIATED RISKS.



