# M365SMP - M365 Services Supplemental Monitoring Management Pack 
The M365 Supplemental Management Pack includes synthetic transactions that provide an increased level of visibility into the health and performance of the Microsoft 365 environment making it the perfect companion to the M365 Admin Portal. The synthetic transactions will be executed from a local point-of-presence (Watcher Node) within the customer network for a comprehensive view of service availability and performance.  

3/11/2023

- Added Teams Network Assessment Tool and MP, provides an additional layer to our already comprehensive Teams monitoring!
- Teams NAT: Updated PacketLossRate to PacketLossRatePercent for rule and monitor
- Agent Proxy Task – Allows to Set Proxy independently
- Fixed Counter name for Verify Chat Duration performance rule
- Updated Mailflow cleanup rule defaults: Interval: 43400->3600, MaxToDelete: 500-1000
- Added ability to control the size of test file for OneDrive and SharePoint Online synthetic transactions, added orphaned file cleanup routine.
- Added auto cleanup of incident messages for M365 Services, added incident number to incident alert names.
- Fixed DirectoryPercentConsumed/DirectoryPercentFree calculations for the M365 Organizational monitor.
- Updated PowerBI Template providing easy to consume indicators for IT staff and Leadership! (requires min PowerBI Desktop ver 2.110.805.0) 


## [Download Here][Download]

[Download]: https://github.com/monitoringguys/M365SMP/releases/download/M365SMPv3/M365.Supplemental.MP-V3.zip
