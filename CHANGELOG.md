# v1902
* Improvement: Errors and warnings during ABAP export are copied to Teamscale worker logging
* Improvement: RFC function to unlock export history vis Teamscale service *clear-abap-history-id-lock*
* Fix: Missing coverage export if option *"Include code coverage data in incremental exports, regardless of code changes"* is specified
* Fix: Show error in Teamscale if export history  id. is locked in SAP system

# v1812
* Feature: Full exports from the SAP system can now be scheduled asynchronously by using background RFC calls, **requires Teamscale 4.7 or later**.  
To use this feature, it is required that background RFC is configured accordingly in the SAP system (transaction `SBGRFCCONF`, see user guide section ...). Furthermore the SAP user for Teamscale must be additionally authorized to execute function modules `BGRFC_CHECK_UNIT_STATE_SERVER`, `BGRFC_DEST_CONFIRM`, `BGRFC_DEST_SHIP`. The default role configuration (in transport *CQRK900046*) is updated to match the new requirements.
* Improvement: The new default role definition (transport *CQRK900046*) for the SAP user is more restrictive, besides function group `/CQSE/TEAMSCALE_CONNCT_RFC` only access to the specific function modules of SAP base system, which are required for RFC communication, are allowed. 

# v1810
* Fix: Findings for ABAP where not shown in the Code Inspector check for displaying Teamscale findings, also the findings were not shown in SE80 or on transport release.

# v1807
* Fix: When exporting code generated from BW objects, transformations were missing in v18.05
* Fix: SCOV status files for monitoring also in incremental exports
* Improvement: Better logging in some error cases
