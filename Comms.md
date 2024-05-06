# Executive Communications
During a critical security incident, executives play a pivotal role by understanding severity, aligning teams, and building stakeholder trust. While employee-wide updates focus on internal coordination, customer notifications prioritize transparency and reputation management

## Key attributes:
- Length: Short
- Timeline: Transparent
- Update: Includes mitigation steps 
- Tone: Urgent and professional

# Email template

**Subject: Time Sensitive Security Update**

**Summary**
OmniRetail Solutions Security team identified a security incident that involved unauthorized access to customer information.  Based on the analysis to date, we believe that thePII data of approximately 1 million customers (including names, addresses, phone numbers, email addresses, and dates of birth) was accessed and removed from the environment. The indicators associated with the attack suggest that a known Chinese state actor (UNC484) is behind the attack. 

### Incident Timeline (all times in PT)
- April 22, 2024 (10:00 pm): Unauthorized access gained to the environment through an unpatched security vulnerability on an external facing server. The access was used to move laterally across the network and escalate privileges. 
- April 24, 2024 (3:00 am) The unauthorized entity accessed an unencrypted copy of our customer database dump. Shortly after, the file was encoded and removed from the environment along with other confidential files (~3GB)
- April 26, 2024 (8:00 pm) The incident was identified by the security monitoring team, following attempts to deploy ransomware in the environment. 
- May 1, 2024 10:00 am - Confirmed access to PII as part of the incident

### Mitigation Status
- Outside Counsel and a specialized forensics firm were has engaged on 04/26
- The incident was mitigated on 04/27 when the unauthorized access was revoked.
- Additional scans of the environment were completed since  4/27 -  did not identify any additional critical vulnerabilities on our external facing servers.
- The leaked documents were not seen online or on the darkweb at this point.

### Next Steps:
The investigation of the incident is still on-going and could reveal additional exposure. Daily briefing will be held going forward at 8 am and 4 pm PT.  

Given the known data exposure, we are under the 72 hour reporting window and will need to complete both regulatory reporting and customer notification by May 4, 10 am PT. 

Sincerely,
[Your Name]
OmniRetail Solutions
