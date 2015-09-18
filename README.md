OpenPilot Turn To Home for CC and CC3D Boards 
=============================================

OpenPilot support for the CC and CC3D boards and variants ceased with OpenPilot-RELEASE-15.02.02. The source repositories for this revision were available on the OpenPilot site at the time of writing (18 Sept 2015).

Support for return to home (RTH) and navigation generally for these boards was displaced by other functionality some time ago. This occured well prior to the 15.02.02 release. It has been widely stated incorrectly that RTH was no longer possible within the available space on the ArmF321xx processor.

The files contained in this repository restore RTH or more correctly turn to home (TTH) by bypassing the original path planning and execution schemes.

The solution adopted is to use the GPS course made good to calculate either a roll or yaw correction for fixed wing aircraft. Muticopters use yaw correction only with the simple expedient of pitching forward thus establishing a course over ground. Altitude hold may be added trivially for most sedate powered gliders and the stubs for this are also given. The assumption however is that the aircraft is still visible but orientation has been lost and that altitude is being managed by the pilot.

The "opfw" firmware files may be posted at a later date.

These files are provided under the GNU Public License (GPL) Version 3 and are for information and use by those who accept ANY AND ALL ASSOCIATED RISKS.



