# Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg; v2308

This archive contains the transport files for the *Teamscale Connector for 
SAP Netweaver&reg; AS ABAP&reg;*. This is required for the connection of 
[Teamscale](https://www.teamscale.com) to a SAP Netweaver AS ABAP instance 
to allow analysis of ABAP code, tests and/or custom code usage within *Teamscale*.

The *Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg;* is compatible with SAP NetWeaver AS ABAP 7.0 EHP2 and later versions, the extension for Test Impact Analysis (TIA) requires SAP NetWeaver AS ABAP 7.50 or later.
It should work on earlier versions, but this has not been tested. 

## Download 
To get the connector, download the [release Zip archive](https://github.com/cqse/teamscale-sap-abap-connector/archive/v2308.zip).

## Version Info
Current release: **Version 2308**, originally provided for Teamscale v9.0
Release date: 2023-08-11

## Contents
The archive comprises the following transports (in the *transports* folder):

**CQRK900160** (files K900160.CQR / R900160.CQR)  
 This is the main transport, objects are in `/CQSE/` namespace and within package `/CQSE/TEAMSCALE_CONNECTOR` and its subpackages.  

**Always required, should be transported first.**  

**CQIK901181** (files K901181.CQI / R901181.CQI)  
This is an extension to support Test Impact Analysis (TIA) within Teamscale. Objects are in `/CQSE/` namespace and within package `/CQSE/TEAMSCALE_TIA` and its subpackages.

**Optional, but requires main transport above. It is recommended to transport if target system is of NW AS ABAP 7.50 or higher. Might not be compatible with earlier versions.**

**CQRK900145** (files K900145.CQR / R900145.CQR)  
This includes a default role (`/CQSE/TEAMSCALE_RFC`) for RFC access from Teamscale server to the Teamscale Connector for SAP Netweaver ABAP. This role can be assigned  to technical user accounts which should be used by Teamscale server.  

**Optional, alternatively an appropriate role can be defined manually, see [section *Authorizations for SAP Teamscale User* in the Teamscale documentation](https://docs.teamscale.com/tutorial/sap-integration/#authorizations-for-sap-teamscale-user).**

## Installation
For transport, place the K* files in the 'cofiles' and  the R* files in the 
'data' directories within the transdir of your host machine (typically 
`/usr/sap/trans` or `C:\usr\sap\trans`) and import the transport with transaction 
STMS. **Enable special conditions *overwrite originals* and *ignore invalid 
component version*** (if applicable - on some SAP Netweaver&reg; systems this option is not available). 

For further details see [section *SAP® Integration* in the Teamscale documentation](https://docs.teamscale.com/tutorial/sap-integration/). 

## Deletion
If you want to remove the *Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg;*, we can provide deletion transport files, on demand.

## License
**&copy; 2023 CQSE GmbH**

**Usage of this software and all its components is restricted to a
valid license for Teamscale (enterprise edition).**

**Static or dynamic analysis of this software or any of its components is prohibited unless the complete results of the analysis are shared with CQSE GmbH.**

