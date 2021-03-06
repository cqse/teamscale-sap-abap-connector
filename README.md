# Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg; v2103

This archive contains the transport files for the *Teamscale Connector for 
SAP Netweaver&reg; AS ABAP&reg;*. This is required for the connection of 
[Teamscale](https://www.teamscale.com) to a SAP Netweaver AS ABAP instance 
to allow analysis of ABAP code, tests and/or custom code usage within *Teamscale*.

The *Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg;* is compatible with SAP NetWeaver AS ABAP 7.0 EHP2 and later versions, the extenstion for Test Impact Analysis (TIA) requires SAP NetWeaver AS ABAP 7.50 or later.
It should work on earlier versions, but this has not been tested. 

## Download 
To get the connector, download the [release Zip archive](https://github.com/cqse/teamscale-sap-abap-connector/archive/v2103.zip).

## Version Info
Current release: **Version 2103**, originally provided for Teamscale v6.7  
Release date: 2021-03-04

## Contents
The archive comprises the following transports (in the *transports* folder):

**CQRK900115** (files K900115.CQR / R900115.CQR)  
 This is the main transport, objects are in `/CQSE/` namespace and within package `/CQSE/TEAMSCALE_CONNECTOR` and its subpackages.  

**Always required, should be transported first.**  

**CQIK900928** (files K900928.CQI / R900928.CQI)  
This is an extenstion to support Test Impact Analysis (TIA) within Teamscale. Objects are in `/CQSE/` namespace and within package `/CQSE/TEAMSCALE_TIA` and its subpackages.

**Optional, but requires main transport above. It is recomended to transport if target system is of NW AS ABAP 7.50 or higher. Might not be compatible with earlier versions.**

**CQRK900117** (files K900117.CQR / R900117.CQR)  
This includes a default role (`/CQSE/TEAMSCALE_RFC`) for RFC access from Teamscale server to the Teamscale Connector for SAP Netweaver ABAP. This role can be assigned  to technical user accounts which should be used by Teamscale server.  

**Optional, alternatively an appropriate role can be defined manually.**

## Installation
For transport, place the K* files in the 'cofiles' and  the R* files in the 
'data' directories within the transdir of your host machine (typically 
`/usr/sap/trans` or `C:\usr\sap\trans`) and import the transport with transaction 
STMS. **Enable special conditions *overwrite originals* and *ignore invalid 
component version*** (if applicable - on some SAP Netweaver&reg; systems this option is not available). 

For further details see [section *SAP® Integration* in the Teamscale documentation](https://docs.teamscale.com/tutorial/sap-integration/). 

## License
**&copy; 2021 CQSE GmbH**

**Usage of this software and all its components is restricted to a
valid license for Teamscale (enterprise edition).**

**Static or dynamic analysis of this software or any of its components is prohibited unless the complete results of the analysis are shared with CQSE GmbH.**

