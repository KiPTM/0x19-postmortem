Postmortem: Outage of Online Marketplace Service
Issue Summary
      Duration of Outage:
      Start Time: July 1, 2024, 14:00 GMT
      End Time: July 1, 2024, 16:30 GMT
      Impact:
      The online marketplace service was completely unavailable.
      Users experienced inability to browse, purchase, or manage products.
      100% of users were affected, with approximately 50,000 users impacted during peak hours.
      Root Cause:
      A misconfigured firewall rule blocked the database server from communicating with the web application.
      Timeline
      14:00 GMT:
      Issue Detected: Monitoring alert triggered by the application health check system.
      14:05 GMT:
      Detection Method: The monitoring system alerted the on-call engineer to a failure in database connectivity.
      14:10 GMT:
      Actions Taken:
      The web application logs were checked, revealing repeated database connection errors.
      Network configurations and database server health were reviewed.
      14:25 GMT:
      Misleading Investigation:
      Initial assumption was that the database server might be down due to high traffic.
      Database server was confirmed operational, misleading focus towards application code.
      14:45 GMT:
      Escalation: Incident was escalated to the network engineering team.
      15:00 GMT:
      Further Investigation:
      Network engineering identified a recent change in firewall rules that restricted necessary database communication.
      15:15 GMT:
      Resolution Actions:
      Firewall rules were corrected to allow database traffic.
      Connectivity was restored and web application functionality was verified.
      16:30 GMT:
      Issue Resolved: Full service was restored, and all systems were confirmed operational.
Root Cause and Resolution
Root Cause:
      The database server was inaccessible due to a misconfigured firewall rule implemented during a routine security update. The rule inadvertently blocked              incoming and outgoing traffic from the database server to the web application servers.
Resolution:
      The firewall configuration was reviewed and corrected to re-enable the required database communication paths. Once the firewall rules were adjusted, normal         database connectivity was restored. Comprehensive tests were performed to ensure no other configurations were impacted.
      Corrective and Preventative Measures
Improvements and Fixes:
                                Enhance firewall rule change management procedures.
                                Implement additional monitoring and alerting for network configuration changes.
                                Regularly review and audit firewall configurations to prevent misconfigurations.
Task List:

Patch Firewall Configuration: 
                                Update and patch the firewall rule set to ensure proper communication paths are maintained.
Add Monitoring: 
                                Implement monitoring on firewall rule changes and database connectivity.

Update Change Management Process: 
                                Incorporate a more robust change review and approval process to prevent accidental misconfigurations.

Conduct Training: 
                                Provide additional training for network engineers on the importance of comprehensive testing and impact analysis of firewall changes.

Periodic Audits: 
                                Schedule regular audits of firewall configurations and network settings to ensure compliance with operational requirements.
Automate Testing: 
                                Develop and deploy automated tests that can validate database connectivity after network changes.
