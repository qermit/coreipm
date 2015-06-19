See http://www.coreipm.com for documentation, latest information, licensing,
support and contact details.


coreIPM provides monitoring, control and inventory tracking functions. It can monitor sensors such as those for temperature, voltage, fan operation, power supply, security, hardware errors and provide logging and alerts. Control functions enable power control and resets. Inventory tracking makes field replaceable unit data available for management.

coreIPM is an open source management architecture for platform management. It is designed to manage systems that can range from an individual board to more complex configurations that can be made up of any combination of boards, blades, enclosure controllers, and multiple enclosure aggregations.

coreIPM is compliant with the Intelligent Platform Interface Management (IPMI) v2.0 with PICMG 3.0 [R2](https://code.google.com/p/coreipm/source/detail?r=2).0 AdvancedTCA extensions.

coreIPM provides monitoring, control and inventory tracking functions. It can monitor sensors such as those for temperature, voltage, fan operation, power supply, security, hardware errors and provide logging and alerts. Control functions enable power control and resets. Inventory tracking makes field replaceable unit data available for management.

coreIPM architecture is comprised of the coreBMC (Baseboard Management Controller) and coreSMC (Shelf Management Controller) hardware & software modules.

coreBMC is fully sufficient by itself to provide board management functions. Coupled with coreSMC it’s possible to build shelves and higher hardware hierarchies such as an ATCA chassis.

coreBMC is currently supported on ARM based microcontrollers. Work in progress to support other microcontroller families.

coreBMC is independent of a main motherboard processor (the payload or host) and its peripherals, BIOS, OS, payload power and system management software that runs on the payload processor. It provides in-band access to management functions at all times.

coreBMC can be built into a motherboard, a blade carrier, a shelf manager or packaged in an OPMA module.

The coreSMC is UNIX/LINUX based and is compliant with the shelf management requirements of the AdvancedTCA specification. coreBMC provides the front-end hardware interfaces to the SMC in a shelf management configuration.

coreBMC

coreBMC is the basic building block which integrates all system management fuctions into an off the shelf single chip microcontroller. Single chip solution saves board space and improves reliability.

Mix/match microcontrollers Initial support for the NXP 32-bit LPC2000 microcontroller family based on ARM7 core. Work in progress to support microcontroller families from other vendors. Use the controller best suited for the task. Currently 32+ microcontroller devices to choose from. These controllers are designed for use in a range of applications requiring high performance and low power consumption in a cost-effective package. Wide range of peripherals including multiple serial interfaces, 10-bit ADC and external bus options.

Supported peripherals and features • i2c • timers • general purpose IO pins • RS232 • SPI • A/D • PWM fan control • Watchdog Timer and Real-Time Clock with battery backup • Ethernet with lwIP TCP/IP stack • USB 2.0 • edge or level sensitive external interrupt pins • In-System Programming/In-Application Programming (ISP/IAP).

Development Full set of development tools using either gcc or commercial compilers and debuggers from multiple vendors. JTAG interface enables FLASH downloads and on-chip debugging. EmbeddedICE RT and Embedded Trace interfaces offering real-time debugging. Full customization and porting services available.

Licensing Dual licensing model. Both GPL and commercial licensing is available. The Open Source GNU General Public License (GPLv2) makes the source code freely available and distributeable to unlimited levels of sublicensees, but requires re-licensing in source code format, on identical terms, including changes and additions. Commercial licensees get a commercially supported product without a requirement that their coreIPM-based software be Open Sourced. The two licensing models cover identical products. To download the source code, contact the developers and other information please visit the project web site http://code.google.com/p/coreipm/.

Messaging interfaces • System Interface - Terminal mode (to payload or shelf manager) • Serial Interface - Terminal mode Serial port sharing Serial port switching Console redirection • IPMB (i2c) • LAN

Message Bridging Routing between System Interface, Serial Interface, IPMB and LAN.

Diagnostics ipmi\_test: Linux based test program for exercising IPMI features, can be used as a basis for building a shelf manager. Also used for firmware updates.

IO capabilities • i2c (IPMB & local bus) • RS232 • General purpose IO for latches, LEDs, E-keying and other uses • 10/100 Ethernet (on select microcontrollers) • USB (on select microcontrollers)

IPMI 2.0 and PICMG 3.0 Support IPMI 2.0 & PICMG 3.0 Release 2.0 compliant. All mandatory commands implemented. Easy to add additional command support. ATCA state management.

• IPM Device “Global” Commands Get Device ID Cold Reset Warm Reset Get Self Test Results Broadcast “Get Device ID”

• BMC Watchdog Timer Commands Reset Watchdog Timer Set Watchdog Timer Get Watchdog Timer

• BMC Device and Messaging Commands Set BMC Global Enables Get BMC Global Enables Clear Message Flags Get Message Flags Get Message Send Message Get BT Interface Capabilities Master Write-Read

• Event Commands Set Event Receiver Get Event Receiver Platform Event

• PEF and Alerting Commands Get PEF Capabilities Arm PEF Postpone Timer Set PEF Configuration Parameters Get PEF Configuration Parameters Set Last Processed Event ID Get Last Processed Event ID

• Sensor Device Commands Get Device SDR Info Get Device SDR Reserve Device SDR Repository Get Sensor Reading

• FRU Device Commands Get FRU Inventory Area Info Read FRU Data Write FRU Data

• SDR Device Commands Get SDR Repository Info Reserve SDR Repository Get SDR

• AdvancedTCA® and PICMG® specific request commands Get PICMG Properties Get Address Info FRU Control Get FRU LED Properties Get LED Color Capabilities Set FRU LED State Get FRU LED State Set IPMB State Set FRU Activation Policy Get FRU Activation Policy Set FRU Activation Get Device Locator Record ID Compute Power Properties Set Power Level Get Power Level Get Fan Speed Properties Set Fan Level Get Fan Level

Other capabilities • USB disk emulation for booting the payload off the management LAN.


coreIPM-LINUX

coreIPM-LINUX is a fully fledged Linux distribution for OMAP 35xx architecture with built in support for coreIPM management architecture.

coreIPM-LINUX provides a ready to use, extremely compact drop in solution for platform management. It is specifically targeted towards shelf and appliance management.

Supported features

• coreIPM interface for controlling multiple i2c buses and general purpose IO pins for latches, LEDs, backplane addressing, HW control and other uses

• RS232 debug port & command line interface

• RMCP+ network interface for sending and receiving IPMI commands

• SNMP Trap generation, SNMP server & MIB for platform management.

• OpenHPI server with coreIPM OpenHPI plug-in. HPI provides a standard and hardware independent service to upper level management software to set and retrieve configuration or operational data about the hardware components, and to control the operation of those components.

Development

The distribution includes the following components in pre-built and source form: x-loader, u-boot, LINUX kernel, BusyBox, CodeSourcery GNU ARM tools, flash utilities, coreIPM components.