OpenPilot Configuraton for RTH
==============================

It is assumed that you have tuned your PID parameters using accepted techniques described elsewhere. Be aware that the fixed wing PID coefficients are generaly of a significantly lower value than that for multicopters.

The RTH home function is intended to be used for model aircraft with:
  * Ailerons
  * Elevons
  * Rudder and elevator only
  
and that are of a sedate nature typically aircraft such as Radians, EasyStars, Bixlers and wings such as the Phantom.

It may also be used for multicopters but that has not been tested extensively.

##General##

The RTH function is controlled using a pot/knob connected to Accessory 0. If the pot is centred then RTH is inactive. If turned in the appropriate direction the aircraft will turn towards home.  The more the knob is turned the quicker the turn. If turned the other direction the aircraft will steer directly away from the launch/home point. 

RTH should not be used if the windspeed exceeds half the nominal flying spped of the aircraft as it cannot reliably obtain a GPS course over ground. This is obviously so if the aircrafts airspeed is the same as or less than the windspeed. 

##GPS##

The RTH function requires a uBlox GPS unit using binary transmission at 38KBaud.  Refer to the OpenPilot documentation for connecting a GPS unit.  Verify that your GPS does in fact display your position reliably using the OpenPilot GCS.
  
##Ailerons##

For aicraft with ailerons you should choose the ROLL version of the firmware setting roll mode to attitude and pitch to either rate or attitude. Yaw should be set to rate. You can elect to use the YAW version of the firmware but in that case the ailerons may resist the turn in part leading to an adverse interaction however if the aircraft has good self levelling capability you can set the roll mode to rate.

##Elevons##

Elevons are normally used to control flying wings. In most cases flying wings do not have rudders. You should choose the ROLL version of the firmware setting both roll and pitch mode to attitude as there is a tendency for the wing to pitch down in turns. If you wish to control pitch compensation yourself then use rate mode.

##Rudder/Elevator##

The rudder is used to control both yaw and roll. Almost all rudder/elevator aircraft has strong self levelling and you should use the YAW version of the firmware. You should set roll/pitch and yaw to rate mode. If you do choose attitude mode for roll it will most likely result in strong coupling between the RTH yaw correction and the roll attitude correction leading to a corkscrewing motion.

##Multicopters##

Roll and pitch must be set to attitude mode and yaw to rate mode. RTH is acheived by pitching the aircraft forward to a small angle (5 deg). Its behaviour should be the same as aa rudder/elevator aircraft yawing slowly towards home.


This information and the files associated with it are provided under the GNU Public License (GPL) Version 3 and are for information and use by those who accept ANY AND ALL ASSOCIATED RISKS.



