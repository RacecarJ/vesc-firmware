# vesc-firmware
Firmware and configuration files for the Vedder Electronic Speed Controller (VESC) firmware version 5.02. There are firmware builds for the VESC6 MkIII, MkIV, and MkV. 

This is a convenience repository for VESC firmware and configuration files for RACECAR/J.

There is a configuration file for for VESC 6 in the VESC-Configuration/vesc6_upenn_foc.xml.

<h3>Quick install instructions</h3>
This firmware may be flashed using the vesc-tool: https://vesc-project.com/vesc_tool version 3.00.

In the case of the VESC6 MkV, it may be necessary to download the bootloader to the VESC. The bootloader is available in the VESC Tool, Firmware->Bootloader. 

<h4>Bootloader installation instructions</h4>

* Connect your VESC via USB to your host computer. Power on the VESC.
* Open the VESC Tool.
* Click Autoconnect.
* Go to the Firmware section on the left.
* Go to the Bootloader tab at the top.
* Click the Upload button in the bottom-right.
* Click "Write Motor Configuration".
* Click "Write App Configuration".

<h4>Firmware Installation</h4>

* Connect your VESC via USB to your host computer. Power on the VESC.
* Click Autoconnect.
* Go to the Firmware section on the left
* Go to the Custom File tab.
* Click the folder icon and browse to the appropriate VESC_TOOL folder and firmware binary for your VESC.
* Click the Upload button in the bottom-right.

Once this is complete, wait at least 10 seconds before re-connecting to configure additional parameters.

<h3>How the firmware is built</h3>

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

You will also need to enable the correct version of the hardware from the list of #defines. For example the current default in conf_general.h is:
<blockquote>
#define HW60_IS_MK5</blockquote>

Indicating that the firmware build will be for a VESC6 MkV.

The resulting firmware file after the build will be inside the "build" directory: BLDC_4_ChibiOS.bin

Typically you will rename this to something more descriptive.

You can then upload this to the VESC using the VESC tool.

<h3>Notes</h3>

<h4>January 2021</h4>

* This is for version 5.02 of the VESC firmware. There are versions for the VESC6 MkIII, MkIV, and MkV. 
* Install with VESC Tool Version 3.0+  https://vesc-project.com/vesc_tool

<h4>September 2020</h4>

* Add firmware and configuration for the VESC MkIV, firmware version 5.01.

<h4>October 2019</h4>

* Add configuration for VESC 6 Plus
