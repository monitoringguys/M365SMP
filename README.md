# M365 Services Supplemental Monitoring Management Pack 
The M365 Supplemental Management Pack includes synthetic transactions that provide an increased level of visibility into the health and performance of the Microsoft 365 environment making it the perfect companion to the M365 Admin Portal. The synthetic transactions will be executed from a local point-of-presence (Watcher Node) within the customer network for a comprehensive view of service availability and performance.  

2/21/2024 <br>
3.0.1.33
- Library: Improved exception handling in Invoke-WebRequest. Reduced $ThrottlingRequestDelaySec from 5 to 1.5. 
- License: Improved exception handling on Get-StandardToken failure.
- WebRequest_ThrottlingImprovement branch created
- M365ST.TeamsCalendarMon.ps1 - Fixed small error in testing branch statement which was causing a benign but annoying error.
- Minor updates/edits to Management Pack Guide

## [Download Here][Download] 
[Download]: https://github.com/monitoringguys/M365SMP/releases/download/M365SMPv3/M365.Supplemental.MP-V3.0.1.33.zip 


12/7/2023 <br>
3.0.1.28
- Improved error handling and logging for throttling scenarios.
- ExchangeOnline: Added logic to identify and parse optional JSON UPN/SMTPEmailAddress from Sender/Receiver email address values in Exchange watcher config. In rare circumstances the UPN may differ from the SMTPEmailAddress for an account. Email address fields now accept optional JSON object in the following format: {"UPN":  "account@domain.name","EmailAddress":  "email@domain.name"}
- ExchangeOnline: Updated function M365Receive to retrieve from specific folder: Inbox. Improved reliability of test message receipt metrics.
- Teams Network Assessment Tool: Upon installation/reinstallation of TNAT, added logic to preserve (rename) existing config file if it exists.
- Watcher node configuration (new/modify): Improved on-demand discovery; Fixed ModifyWatcherConfig on-demand discovery target name; correctly triggers WatcherNode discovery now.
- License: Updated license sku display names.
- Teams Calendar: Updated the Delete logic (which really, strangely only cancelled the event) to a 'Cancel' which actually cancels the event AND "The action moves the event to the Deleted Items folder." <br>
Cancel: https://learn.microsoft.com/en-us/graph/api/event-cancel?view=graph-rest-1.0&tabs=http <br>
Delete: https://learn.microsoft.com/en-us/graph/api/event-delete?view=graph-rest-1.0&tabs=http <br>

8/7/2023 <br>
3.0.1.5
- Improved Get-AccessToken and Get-StandardToken logging. Fixed Services workflows auth token request. 
- M365ST.TeamsMon.ps1 - Moved the $RequestDelayMS before the stopwatch timer in Verification section.
- M365ST.TeamsCalendarMon.ps1 - **Added
  
6/16/2023
- Improved cleanup routine; added SentItems, added delay between delete operations. Set interval to 86400. Increased MaxItemsToDelete. 
 - Added OnDemand discovery for all m365 class types to the Watcher node "modify configuration" task.
 - Added throttling logic into M365Library.ps1
 - Hardcoded synctime vars for all MPs to help disperse requests to Graph.
 - Changed all configuration tasks IntervalSeconds from $TargetHost property to LEAVE_BLANK_TO_INHERIT_DEFAULT_VALUE
 - Corrected numerous monitor Category tags. Many performance monitors were set as default AvailabilityHealth; updated to PerformanceHealth.
 - Added additional rules and monitors for Licenses  
      Added rules:  
            M365 License - Licenses Consumed (Units) Performance Collection Rule  
            M365 License - Licenses Available (%) Performance Collection Rule  
      Added monitors:  
            M365 License - Licenses Consumed (Units) Monitor  
            M365 License - Licenses Available (Units) Monitor  
- Library, Services, License: Password/ClientSecret Decode and Get-StandardToken functions log critical failures and exit immediately  
      Updated: M365 <namespace> - Script Resource Library Failure Repeated Event Detection Monitor  
            TimerResetSeconds, old:3600, new:$Target/Property.../IntervalSeconds$  
      Updated: M365 <namespace> - Script Failure Repeated Event Detection Monitor  
            <RepeatedRegExEventDisplayNumber>999[5-6]|999[8-9]</RepeatedRegExEventDisplayNumber>  
            TimerResetSeconds, old:3600, new:$Target/Property.../IntervalSeconds$  
      Added: M365 <namespace> - AuthToken Retrieval Failure Repeated Event Detection Monitor  
 - SharePoint, OneDrive: Changed AlertOn from Error to Warning for performance unit monitors.
 - Teams: added TNAT discovery GUID to the "Modify Teams Config" agent task OnDemandDiscovery.
 - SharePoint: Fixed duplicate name issue. Graph has been known to return duplicate identical site entries.
 - Updated a few knowledge articles. Improved a couple class DisplayNames.



