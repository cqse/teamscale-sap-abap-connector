# Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg; v1902 

This archive contains the transport files for the *Teamscale Connector for 
SAP Netweaver&reg; AS ABAP&reg;*. This is required for the connection of 
[Teamscale](https://www.teamscale.com) to a SAP Netweaver AS ABAP instance 
to allow analysis of ABAP code, tests and/or custom code usage within *Teamscale*.

The *Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg;* is compatible with SAP NetWeaver AS ABAP 7.0 EHP2 and later versions.
It should work on earlier versions, but this has not been tested.

## Download 
To get the connector, download the [release Zip archive](https://github.com/cqse/teamscale-sap-abap-connector/archive/v1902.zip).

## Version Info
Current release: **Version 1902**, originally provided for Teamscale v4.8.4  
Release date: 2019-02-22

## Contents
The archive comprises the following transports (in the *transports* folder):

**CQRK900060** (files K900060.CQR / R900060.CQR)  
 This is the main transport, objects are in /CQSE/ namespace and within package /CQSE/TEAMSCALE_CONNECTOR and its subpackages.  
**Always required, should be transported first.**  

**CQRK900046** (files K900046.CQR / R900046.CQR)  
This includes a default role (/CQSE/TEAMSCALE_RFC) for RFC access from Teamscale server to the Teamscale Connector for SAP Netweaver ABAP. This role can be assigned  to technical user accounts which should be used by Teamscale server.  
**Optional, alternatively an appropriate role can be defined manually.**

## Installation
For transport, place the K* files in the 'cofiles' and  the R* files in the 
'data' directories within the transdir of your host machine (typically 
/usr/sap/trans or C:\usr\sap\trans) and import the transport with transaction 
STMS. **Enable special conditions *overwrite originals* and *ignore invalid 
component version*** (if applicable - on some SAP Netweaver&reg; systems this option is not available). 

For further details see Teamscale [user guide](https://www.cqse.eu/download/teamscale/userguide.pdf), chapter 6.

## License
**&copy; 2019 CQSE GmbH**

**Usage of this software and all its components is restricted to a
valid license for Teamscale (enterprise edition).**

**Static or dynamic analysis of this software or any of its components is prohibited unless the complete results of the analysis are shared with CQSE GmbH.**

