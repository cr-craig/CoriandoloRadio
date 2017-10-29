# CoriandoloRadio
This respository contains source code for the Coriandolo Radio protocol; it also contains documentation, "wrappers" and example code.

This code executes on the Nordic Semiconductor nRF51 processor (any device in that family).  A software version for the Nordic Semiconductor nRF52 processor is in debug; source code for the nRF52840 processor is included with this release.  Versions for other CPU/Radio combinations are possible, but not planned at this time.

The software was developed and tested using the Keil IDE.  A free version for Cortex-M0 processors is available from Keil.  The nRF52 version will operate on the 32K limited version of the Keil tools.

This code has been downloaded and run on the CR1 DevKit hardware.  Information about hardware radio modules can be found at: http://www.coriandoloradio.com


Files in repository
IMPORTANT NOTE: Release on 2017-10-29 contains a correction in the radio hardware drivers.  Sometime this spring, an unintentionaly change was made to the register settings for the radio addresses used by Coriandolo Radio.  Although this change was internally consistent (SENOR and BASE could communicate), the radio addresses did not match the documentation.  The 2017-10-29 release corrects this.

"2017-10-29 1130 CR Protocol Release.zip"  -- contains all of the source code for Coriandolo Radio Protocol 

"2017-10-29 1134 CR Protocol Doxygen Output.zip" -- contains html files of Doxygen documentation

"A brief description of Coriandolo Radio.pdf" -- documentation of Coriandolo Radio protocol

"Selecting Microprocessor for Coriandolo Radio" -- instructions to select either nR51822 and nRF52840 microprocessor as Keil target.


Radio hardware driver code for both nRF51 and nRF52840 processors are included in the release.  Also included is the "CR Simple" wrapper - an easier to use API for CR.

The release includes two "main" files, which can be used for testing the protocol on CR1 radio modules.  "RadioTest_CR" blinks the LEDs on the SENSOR and BASE to indicate how many messages were received in an exchange; in a "perfect" exchange the SENSOR LED will blink 8 times and the BASE LED will blink 9 times (extra blink for the Announcement).  "SpeedTest_CR" simulates sending 256 messages with 250 bytes of payload from a SENSOR to a BASE; using a debugger the code can provide a time in microseconds for receiving 64000 bytes of payload.  Documentation for both of these tests are within the code.

Please Note:  The transmit message SYNC option is under development; code is included in this release.  This option may be selected; messages with timestamps appear to be transmitted; code for performing clock synchronization is not included in the release.  We will be testing code for clock synchronization in the fall of 2017.  I hope to have a CR Wrapper available around (plus or minus) year-end 2017.

