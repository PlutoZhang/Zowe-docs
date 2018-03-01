# Fault Analyzer APIs

Review the following table for detailed information about Fault Analyzer APIs. To use the Fault Analyzer APIs, Fault Analyzer must be installed.

|REST API|Description|Scenario|Prerequisites|
|--------|-----------|--------|-------------|
|`GET /FaultAnalyzer/api/historyFiles/defaultHistoryFile`|Get the Fault Analyzer default history file name.|Use this API to get the Fault Analyzer default history data set name that is specified in IDICNFxx parmlib member.|Fault Analyzer

Fault Analyzer microservice

|
|`GET /FaultAnalyzer/api/historyFiles/{historyFile}`|Get attributes of a history file.|Use this API to get the attributes of a Fault Analyzer history file.|Fault Analyzer

Fault Analyzer microservice

|
|`GET /FaultAnalyzer/api/historyFiles/{historyFile}/faultEntries`|Get a list of fault entries for a history file.|Use this API to get a list of fault entry member names that reside in the specified Fault Analyzer history file.|Fault Analyzer

Fault Analyzer microservice

|
|`Delete /FaultAnalyzer/api/historyFiles/{historyFile}/faultEntries/{faultEntry}`|Delete a fault entry.|Use this API to permanently delete a fault entry from a nominated Fault Analyzer history file. Locked fault entries cannot be deleted.|Fault Analyzer

Fault Analyzer microservice

|
|`GET /FaultAnalyzer/api/historyFiles/{historyFile}/faultEntries/{faultEntry}`|Get attributes of a fault entry.|Use this API to get a set of attributes that are associated with a nominated fault entry in a Fault Analyzer history file.|Fault Analyzer

Fault Analyzer microservice

|
|`POST /FaultAnalyzer/api/historyFiles/{historyFile}/faultEntries/{faultEntry}`|Generate or refresh a fault entry report.|If the fault entry report is not available or needs to be regenerated, use this API to generate or refresh a report for a nominated fault entry.|Fault Analyzer

Fault Analyzer microservice

|
|`GET /FaultAnalyzer/api/historyFiles/{historyFile}/faultEntries/{faultEntry}/report`|Get a report for a fault entry.|Use this API to get a Fault Analyzer report or report section that is associated with a nominated fault entry. The report is returned in a JSON object, and can be formatted as TEXT, HTML, or JSON. By default, the full report is returned, but you can use the section query parameter to return a single section of the report if available.|Fault Analyzer

Fault Analyzer microservice

|

**Parent topic:** [Using Atlas REST APIs](../topics/usingatlasrestapis.md)

