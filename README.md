# How to use

## vf2-imager
Compile EPOS application and get the binary file. Then run the imager with the binary file as input.

`./vf2-imager -i <input-file>.bin -o <output-file>.img`

## vf2
Set SBC to boot from UART (11 in boot mode switch) and connect UART GPIO stick to the computer. Then run this application with the image file as input (the image file is the output from the imager). If serial port not found, disconnect and reconnect the UART GPIO stick.

Must be run as root.

`./vf2 <output-file>.img`

To run the compiled EPOS application, change the boot mode switch to 00 and restart the SBC.

## rduart
Run this application to read the output from the SBC. 

Must be run as root.

`./rduart`


## Observations
The tools here provided were compiled for Ubuntu 22.04 with x86_64 architecture. In case of other OS or architecture, the tools must be recompiled from source, installing the necessary dependencies (https://github.com/zyedidia/blog-code/tree/master/2-baremetal-visionfive/tools).

To run the EPOS application in the SBC, we must change the existing firmware, uploading a new one. To revert back to the original firmware, just run the vf2 program again with the image file contained in this repository (visionfive2_fw_payload.img).