OpenPilot Configuration for RTH
===============================

The RTH function is intended to provide a reasonable effort to bring relatively sedate aircraft such as Radians, EasyStars, Bixlers and flying wings such as the Phantom towards the launch point or home. You should read the Disclaimer below.

The RTH home function is intended to be used for model aircraft with:
  * Ailerons
  * Elevons
  * Rudder and elevator only

It may also be used for multicopters but that has not been tested extensively.

##Important##

It is assumed that you have tuned your PID parameters using accepted techniques described elsewhere. The RTH function supplies roll angles or turn rates and expects the PID loops to be tuned such that the aircraft will follow these commanded values. Be aware that the fixed wing PID coefficients are generally of a significantly lower value than that for multicopters. 

You should also make sure your Tx rates or control throws are sufficient to override the flight controller. Relying on the mode switch to get you out of trouble is "courageous".

##General##

The RTH function is controlled using a pot/knob connected to Accessory 0.  The more the pot is turned the quicker, or more aggressive, the turn. If you find that the aircraft actually turns away from the launch/home point you will have to reverse the channel sense for the pot. 

![https://github.com/gke/OpenPilot-RTH/blob/master/wiki/graphics/Acc0.JPG](https://github.com/gke/OpenPilot-RTH/blob/master/wiki/graphics/Acc0.JPG)

Chan 7 can of course be whatever is most appropriate on your Tx.

RTH should not be used if the windspeed exceeds half the nominal flying speed of the aircraft as it cannot reliably obtain a GPS course over ground. This is obviously so if the aircraft's airspeed is the same as or less than the windspeed.

Check everything several mistakes high.

##GPS##

The RTH function requires a uBlox GPS unit using binary transmission at 38KBaud.  Refer to the OpenPilot documentation for connecting a GPS unit.  Verify that your GPS does in fact display your position reliably using the OpenPilot GCS.
  
##Ailerons##

For aircraft with ailerons you should choose the ROLL version of the firmware setting roll mode to attitude and pitch to either rate or attitude. Yaw should be set to rate. You can elect to use the YAW version of the firmware but in that case the ailerons may resist the turn in part leading to an adverse interaction however if the aircraft has good self levelling capability you can set the roll mode to rate.

##Elevons##

Elevons are normally used to control flying wings. In most cases flying wings do not have rudders. You should choose the ROLL version of the firmware setting both roll and pitch mode to attitude as there is a tendency for the wing to pitch down in turns. The self levelling on the pitch axis may still not be enough. If you wish to control pitch compensation yourself then use rate mode.

##Rudder/Elevator##

The rudder is used to control both yaw and roll. Almost all rudder/elevator aircraft has strong self levelling and you should use the YAW version of the firmware. You should set roll/pitch and yaw to rate mode. If you do choose attitude mode for roll it will most likely result in strong coupling between the RTH yaw correction and the roll attitude correction leading to a corkscrewing motion.

##Multicopters##

Roll and pitch must be set to attitude mode and yaw to rate mode. RTH is achieved by pitching the aircraft forward to a small angle (5 deg). Its behaviour should be the same as aa rudder/elevator aircraft yawing slowly towards home.

##Is it Working?##

In most cases you will not have GCS on the flight line, so you should monitor the CC/CC3D board LEDs. The Blue LED will change from a simple "heartbeat" blink every second to being on most of the time in a flickering manner once the home position has been obtained. At this point you should select the staibilisation mode you will be using then turn the RTH pot/knob to its maximum value. You should see the appropriate control surface(s), depending on whether you are using YAW or ROLL firmware, move. 

The RTH function always thinks it is flying and will produce corrections even if sitting on the ground.  For this reason make sure the pot to its minimum setting before takeoff.

##Disclaimer##

This information and the files associated with it are provided under the GNU Public License (GPL) Version 3 and are for information and use by those who accept ANY AND ALL ASSOCIATED RISKS.



