# Hello example for IMXRT1050-EVKB
# Updated: 11/11/24 @ 11:57

Simple Hello World example for NXP [IMXRT1050-EVKB](https://www.nxp.com/part/IMXRT1050-EVKB#/) Evaluation Kit.
This example prints "Hello World" and a counter value via the standard output which is routed to the debug console through Virtual COM port.

[![Keil Studio Cloud - Import Project](https://img.shields.io/badge/Keil_Studio_Cloud-Import_Project-0091bd?logo=arm&logoColor=0091bd)](https://studio.keil.arm.com/?import=https://github.com/Arm-Examples/Hello_IMXRT1050-EVKB.git)
[![example workflow](https://img.shields.io/github/actions/workflow/status/Arm-Examples/Hello_IMXRT1050-EVKB/ci.yml?logo=arm&logoColor=0091bd&label=Example%20Published)](https://www.keil.arm.com/) 
[![CMSIS Compliance](https://img.shields.io/github/actions/workflow/status/Arm-Examples/Hello_IMXRT1050-EVKB/verify.yml?logo=arm&logoColor=0091bd&label=CMSIS%20Compliance)](https://www.keil.arm.com/cmsis) 

## Prerequisites

### Tools:
 - [CMSIS-Toolbox v2.0.0](https://github.com/Open-CMSIS-Pack/cmsis-toolbox/releases) or newer
 - [Microsoft Visual Studio Code](https://code.visualstudio.com/download) with Keil Studio Pack extension (optional, alternatively CLI can be used)
 - [Arm Compiler 6](https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Embedded) (automatically installed when using Visual Studio Code with vcpkg)

### DAPLink Firmware

To be recognized correctly by the Device Manager extension in VS Code, you need to replace the original debug adapter firmware with a DAPLink firmware. Please follow the instructions on [OpenSDA Serial and Debug Adapter](https://www.nxp.com/design/software/sensor-toolbox/opensda-serial-and-debug-adapter:OPENSDA#MIMXRT1050-EVK).

## Build Solution/Project

### Using Visual Studio Code with extensions

Required tools described in file 'vcpkg-configuration.json' should be automatically installed by vcpkg. You can see the status of vcpkg in the status bar.

Required CMSIS packs need to be also installed. In case a required pack is missing, a notification window will pop-up to install the missing pack.

Open the 'CMSIS' view from the side bar, select desired 'Build Type' and press the 'Build' button.

### Using Command Line Interface (CLI)

Download required packs (not required when the packs are already available) by executing the following commands:
   ```sh
   csolution list packs -s hello.csolution.yml -m >packs.txt
   cpackget update-index
   cpackget add -f packs.txt
   ```
Build the project by executing the following command:
```sh
cbuild hello.csolution.yml
```

## Run the application

### Using Visual Studio Code with extensions

 - Connect the board's DAPLink USB to the PC (provides also power).
 - Open the 'CMSIS' view from the side bar:
   - Press the 'Run' button and wait until the image is programmed and starts running.
   - Press the 'Open Serial' button and select the board's serial port with 115200 baud rate.
 - Observe the terminal output.

 ### Using Drag-and-drop programming or external programmer and terminal

 - Connect the board's DAPLink USB to the PC (provides also power).
 - Program the image (.hex) using Drag-and-drop programming or use external programmer.
 - Open terminal on the PC and connect to the board's serial port with 115200 baud rate.
 - Observe the terminal output.

## Debug the application

### Using Visual Studio Code with extensions

Open the 'CMSIS' view from the side bar and press the 'Debug' button.
