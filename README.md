# Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg; v2506

This archive contains the transport files for the *Teamscale Connector for 
SAP Netweaver&reg; AS ABAP&reg;*. This is required for the connection of 
[Teamscale](https://www.teamscale.com) to a SAP Netweaver AS ABAP instance 
to allow analysis of ABAP code, tests and/or custom code usage within *Teamscale*.

The *Teamscale Connector for SAP Netweaver&reg; AS ABAP&reg;* is compatible with SAP NetWeaver AS ABAP 7.40 SP2 and later versions, the extension for Test Impact Analysis (TIA) requires SAP NetWeaver AS ABAP 7.50 or later.
It should work on earlier versions, but this has not been tested. 

## Download 
To get the connector, download the [release Zip archive](https://github.com/cqse/teamscale-sap-abap-connector/archive/v2506.zip).

## Version Info
Current release: **Version 2506**, originally provided for Teamscale v2025.5
Release date: 2025-06-30

## Contents
The archive comprises the following transports (in the *transports* folder):

**CQRK900177** (files K900177.CQR / R900177.CQR)  
 This is the main transport, objects are in `/CQSE/` namespace and within package `/CQSE/TEAMSCALE_CONNECTOR` and its subpackages.  

**Always required, should be transported first.**  

**CQIK900190** (files K900190.CQI / R900190.CQI)  
This is an extension to support Test Impact Analysis (TIA) within Teamscale. Objects are in `/CQSE/` namespace and within package `/CQSE/TEAMSCALE_TIA` and its subpackages.

**Optional, but requires main transport above. It is recommended to transport if target system is of NW AS ABAP 7.50 or higher. Might not be compatible with earlier versions.**

**CQRK900172** (files K900172.CQR / R900172.CQR)  
This includes a default role (`/CQSE/RFC_TEAMSCALE`) for RFC access from Teamscale server to the Teamscale Connector for SAP Netweaver ABAP. This role can be assigned  to technical user accounts which should be used by Teamscale server.  

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

## Migration (Version 2506 or higher)
When updating to version 2506 or higher from an earlier version, manual migration steps might be necessary.
For all *Code Inspector* variants that use the check *Teamscale Findings*, the configuration must be adjusted
to use the new `SM59` connection parameters. The previously configured URL and authentication to the *Teamscale*
server must be now configured via an HTTP destination created in transaction `SM59`. If your SAP System requires
an HTTP(S) proxy in order to connect to the *Teamscale* server, the proxy settings now must be configured in the
HTTP(S) destination. To use PSE (HTTPS certificate), the entry `HTTPS Client (Anonymous)` must be selected. After
creating the `SM59` destinations, the update can be installed and the destinations must be set in the *Teamscale
Findings* parameters. For further details see
[section *Configuring Connection Settings* in the Teamscale documentation](https://docs.teamscale.com/tutorial/sap-integration/#configuring-connection-settings).

## License
**&copy; 2025 CQSE GmbH**

**Usage of this software and all its components is restricted to a
valid license for Teamscale (enterprise edition).**

**Static or dynamic analysis of this software or any of its components is prohibited unless the complete results of the analysis are shared with CQSE GmbH.**

