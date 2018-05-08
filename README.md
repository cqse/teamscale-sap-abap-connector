# Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg; v1805

## License 
**&copy; 2018 CQSE GmbH**  
**Usage of this software and all its components is restricted to a 
valid license for Teamscale (enterprise edition).**

## Version Info
**Version 1805**, originally provided for Teamscale v4.2.x.  
Release date: 2018-05-07

## Summary 
This archive contains the transport files for the *Teamscale Connector for 
SAP Netweaver&reg; AS ABAP&reg;*. This is required for the connection of 
[Teamscale](https://www.teamscale.com) to a SAP Netweaver AS ABAP instance 
to allow analysis of ABAP code, tests and/or custom code usage within *Teamscale*. 

## Download 
To get the connector, download the [release Zip archive](https://github.com/cqse/teamscale-sap-abap-connector/archive/v1805.zip).

## Contents
The archive comprises the following transports (in the *transports* folder):

**CQRK00028** (files K900028.CQR / R900028.CQR)  
 This is the main transport, objects are in /CQSE/ namespace and within package /CQSE/TEAMSCALE_CONNECTOR and its subpackages.  
**Always required, should be transported first.**  

**CQRK00016** (files K900016.CQR / R900016.CQR)  
This includes a default role (/CQSE/TEAMSCALE_RFC) for RFC access from Teamscale server to the Teamscale Connector for SAP Netweaver ABAP. This role can be assigned  to technical user accounts which should be used by Teamscale server.  
**Optional, alternatively an appropriate role can be defined manually.**

## Installation
For transport, place the K* files in the 'cofiles' and  the R* files in the 
'data' directories within the transdir of your host machine (typically 
/usr/sap/trans or C:\usr\sap\trans) and import the transport with transaction 
STMS. **Enable special conditions *overwrite originals* and *ignore invalid 
component version*.** 

For further details see Teamscale [user guide](https://www.cqse.eu/download/teamscale/userguide.pdf), chapter 6.
