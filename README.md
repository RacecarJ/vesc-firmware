# vesc-firmware
Firmware and configuration files for Vedder electronic speed controller VESC MkV.

Convenience repository for VESC firmware and configuration files for RACECAR/J.

The firmware and configuration file are version 5.02 of the firmware.

There is a configuration file for for VESC 6 in the VESC-Configuration/vesc6_upenn_foc.xml.

<h3>How firmware is built</h3>

The general instructions for building the firmware are on the Vedder Github account, bottom of the page:
https://github.com/vedderb/bldc Before building, you will need to change a parameter which tells the firmware to use the PPM port to as an output. We use that to control the steering servo.

<blockquote>
$ git clone https://github.com/vedderb/bldc.git 
</blockquote>
<blockquote>
$ cd bldc
</blockquote>

Edit the file conf_general.h and change:
<blockquote>
#define SERVO_OUT_ENABLE       0
</blockquote>
to:
<blockquote>
#define SERVO_OUT_ENABLE       1
</blockquote>
then you are ready to build:
<blockquote>
$ make
</blockquote>

The resulting firmware file is inside the "build" directory: BLDC_4_ChibiOS.bin

Typically this is renamed to VESC_servoout.bin

You can then upload this to the VESC using the VESC tool.

<h3>Notes</h3>

<h4>November 2020</h4>

* The VESC 6 MkV has been released, but the master branch has not been updated in the Vedder bldc repository. This compilation is from the dev_fw_5_02 branch.

<h4>September 2020</h4>

* Add firmware and configuration for the VESC MkIV, firmware version 5.01.

<h4>October 2019</h4>

* Add configuration for VESC 6 Plus
