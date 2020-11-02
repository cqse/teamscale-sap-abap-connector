# v2010
* Fix: ABAP full batch export blocks incremental exports
* Fix: Low performance of database access to read object meta data
* Fix: Avoid deadlocks due to database locks
* Fix: Dumps in case of assertion violation in CL_TYPE_GATHERER
* Fix: Wrong transport info in commit message

# v2002
* Feature: Plug-in for SAP updates ABAP code in Teamscale on check request (e.g. triggered from ATC, SE80, Code Inspector, Transport System) to include findings for most recent changes, **requires Teamscale Server v5.7.3 or later**.
* Feature: Package hierarchy can be exported for all objects. This is used in architecture analysis to identify dependencies to 3rd-party-types (e.g. objects in SAP standard) on package level, **requires Teamscale Server v5.7.0 or later**.
* Feature: Asynchronous full exports can be scheduled as batch exports. This is the default for asynchronous exports and prevents time-outs occurring in jobs scheduled as background RFC job (bgRFC), **requires Teamscale Server v5.7.0 or later**.
* Improvement: Updated default role definition for Teamscale RFC user to also include authorization to schedule/release batch jobs (required for asynchronous full exports as batch jobs)
* Improvement: SAP version is included in exporter log file
* Fix: Missing dependencies to types specified in ABAP type groups
* Fix: Warnings in Teamscale worker log about files of modifications which cannot be deleted
* Fix: Failing Code Inspector check for unsupported object types 
* Fix: Mal-formatted UXX include of function groups may cause an `CX_SY_READ_SRC_LINE_TOO_LONG` exception

# v1907
* Fix: Finding retrieval for central ATC systems (Requires Teamscale 5.2.1)
* Fix: Unmodified includes of modified standard function groups were exported in full export, but all function modules where reported as deleted in incremental export
* Improvement: Improved ABAP code to avoid possible security findings

# v1906
* Improvement: Group Teamscale data by SAP transport request
* Improvement: Export ABAP Dictionary Objects for Architecture Analysis
* Fix: Importing full ABAP export fails due to duplicated function group include
* Fix: Inconsistent ABAP function groups may cause termination of ABAP export

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
* Feature: Optional enhancement for class `CL_COVERAGE_COLLECT` to avoid any interference with UPL of SAP Solution Manger 
* Fix: When exporting code generated from BW objects, transformations were missing in v18.05
* Fix: SCOV status files for monitoring also in incremental exports
* Improvement: Better logging in some error cases
