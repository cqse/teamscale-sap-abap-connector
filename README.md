# Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg; v1810

This archive contains the transport files for the *Teamscale Connector for 
SAP Netweaver&reg; AS ABAP&reg;*. This is required for the connection of 
[Teamscale](https://www.teamscale.com) to a SAP Netweaver AS ABAP instance 
to allow analysis of ABAP code, tests and/or custom code usage within *Teamscale*. 

The *Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg;* is compatible with SAP NetWeaver AS ABAP 7.0 EHP2 and later versions.
It should work on earlier versions, but this has not been tested.

## Download 
To get the connector, download the [release Zip archive](https://github.com/cqse/teamscale-sap-abap-connector/archive/v1810_incl_enh.zip).

## Version Info
Current release: **Version 1810**, originally provided for Teamscale v4.5.6.  
Release date: 2018-10-10

## Contents
The archive comprises the following transports (in the *transports* folder):

**CQRK900042** (files K900042.CQR / R900042.CQR)  
 This is the main transport, objects are in /CQSE/ namespace and within package /CQSE/TEAMSCALE_CONNECTOR and its subpackages.  
**Always required, should be transported first.**  

**CQRK900016** (files K900016.CQR / R900016.CQR)  
This includes a default role (/CQSE/TEAMSCALE_RFC) for RFC access from Teamscale server to the Teamscale Connector for SAP Netweaver ABAP. This role can be assigned  to technical user accounts which should be used by Teamscale server.  
**Optional, alternatively an appropriate role can be defined manually.**

**CQRK900038** (files K900038.CQR / R900038.CQR)  
This includes an optional enhancement of class `CL_COVERAGE_COLLECT` which copies the content of table `COVRES` when coverage is collected by SCOV. The enhancement is placed in package /CQSE/CUSTOMER.  
**Optional, should be only transported if UPL is active on the SAP system to prevent loss of usage data in rare cases. Typically it is not required.**

## Installation
For transport, place the K* files in the 'cofiles' and  the R* files in the 
'data' directories within the transdir of your host machine (typically 
/usr/sap/trans or C:\usr\sap\trans) and import the transport with transaction 
STMS. **Enable special conditions *overwrite originals* and *ignore invalid 
component version* (if applicable - on some SAP Netweaver&reg; systems this option is not available).** 

For further details see Teamscale [user guide](https://www.cqse.eu/download/teamscale/userguide.pdf), chapter 6.

## License 
**&copy; 2018 CQSE GmbH**  
**Usage of this software and all its components is restricted to a 
valid license for Teamscale (enterprise edition).**
