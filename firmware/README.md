# VESC Configurations
This firmware is for version 5.02 for the VESC6. There are versions for the VESC6 MkIII, MkIV and MkV. Make sure that you select the correct version for your hardware!!! This firmware may damage other versions of the hardware.

These firmware allow for servo control. The firmware is from the Vedder bldc-tool repository: https://github.com/vedderb/bldc-tool

This firmware may be flashed using the vesc-tool: https://vesc-project.com/vesc_tool version 3.00.

In the case of the VESC6 MkV, it may be necessary to download the bootloader to the VESC. The bootloader is available in the VESC Tool, Firmware->Bootloader. 

Bootloader installation instructions:

Connect your VESC via USB to your host computer.
Open the appropriate version of the VESC Tool.
Click Autoconnect.
Go to the Firmware section on the left.
Go to the Bootloader tab at the top.
Click the Upload button in the bottom-right.
Click "Write Motor Configuration".
Click "Write App Configuration".

Firmware Installation:
Connect your VESC via USB to your host computer.
Click Autoconnect.
Go to the Firmware section on the left
Go to the Custom File tab.
Click the folder icon and browse to the appropriate VESC_TOOL folder and firmware binary for your VESC.
Click the Upload button in the bottom-right.
Once this is complete, wait at least 10 seconds before re-connecting to configure additional parameters.



 

