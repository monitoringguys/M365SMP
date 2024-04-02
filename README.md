# M365 Services Supplemental Monitoring Management Pack 
The M365 Supplemental Management Pack includes synthetic transactions that provide an increased level of visibility into the health and performance of the Microsoft 365 environment making it the perfect companion to the M365 Admin Portal. The synthetic transactions will be executed from a local point-of-presence (Watcher Node) within the customer network for a comprehensive view of service availability and performance.  

4/2/2024 <br>
3.0.1.34
- Small issue with License workflows (monitoring and perf) were broken 
- Updated PowerBI Template 

2/21/2024 <br>
3.0.1.33
- Library: Improved exception handling in Invoke-WebRequest. Reduced $ThrottlingRequestDelaySec from 5 to 1.5. 
- License: Improved exception handling on Get-StandardToken failure.
- WebRequest_ThrottlingImprovement branch created
- M365ST.TeamsCalendarMon.ps1 - Fixed small error in testing branch statement which was causing a benign but annoying error.
- Minor updates/edits to Management Pack Guide

## [Download Here][Download] 
[Download]: https://github.com/monitoringguys/M365SMP/releases/download/M365SMPv3/M365.Supplemental.MP-V3.0.1.34.zip 
