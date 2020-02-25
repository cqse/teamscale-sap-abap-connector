# Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg; v2002

This archive contains the transport files for the *Teamscale Connector for 
SAP Netweaver&reg; AS ABAP&reg;*. This is required for the connection of 
[Teamscale](https://www.teamscale.com) to a SAP Netweaver AS ABAP instance 
to allow analysis of ABAP code, tests and/or custom code usage within *Teamscale*.

The *Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg;* is compatible with SAP NetWeaver AS ABAP 7.0 EHP2 and later versions.
It should work on earlier versions, but this has not been tested.

## Download 
To get the connector, download the [release Zip archive](https://github.com/cqse/teamscale-sap-abap-connector/archive/v2002.zip).

## Version Info
Current release: **Version 2002**, originally provided for Teamscale v5.7.3
Release date: 2020-02-12

## Contents
The archive comprises the following transports (in the *transports* folder):

**CQRK900097** (files K900097.CQR / R900097.CQR)  
 This is the main transport, objects are in /CQSE/ namespace and within package /CQSE/TEAMSCALE_CONNECTOR and its subpackages.  
**Always required, should be transported first.**  

**CQRK900092** (files K900092.CQR / R900092.CQR)  
This includes a default role (/CQSE/TEAMSCALE_RFC) for RFC access from Teamscale server to the Teamscale Connector for SAP Netweaver ABAP. This role can be assigned  to technical user accounts which should be used by Teamscale server.  
**Optional, alternatively an appropriate role can be defined manually.**

**CQRK900077** (files K900077.CQR / R900077.CQR)  
This includes legacy reports for backwards compatibility. These reports can be
used to export ABAP code, Code Inspector results and procedure coverage data
in batch jobs. Since they directly create and modify physical files, they
are only recommended if the use of logical files is not possible.
**Optional, only required if older batch jobs are missing reports after the update.**

## Installation
For transport, place the K* files in the 'cofiles' and  the R* files in the 
'data' directories within the transdir of your host machine (typically 
/usr/sap/trans or C:\usr\sap\trans) and import the transport with transaction 
STMS. **Enable special conditions *overwrite originals* and *ignore invalid 
component version*** (if applicable - on some SAP Netweaver&reg; systems this option is not available). 

For further details see [section *SAP® Integration* in the Teamscale documentation](https://docs.teamscale.com/howto/sap/#sap%C2%AE-integration) (for Teamscale server v5.6 or earlier: chapter 6 in the user guide PDF). 

## License
**&copy; 2020 CQSE GmbH**

**Usage of this software and all its components is restricted to a
valid license for Teamscale (enterprise edition).**

**Static or dynamic analysis of this software or any of its components is prohibited unless the complete results of the analysis are shared with CQSE GmbH.**

