Overview:
- OmniRetail Solutions is a global retail company with a workforce of 15,000 employees across multiple countries, including the US, UK, Japan, and Singapore.
- Known for its extensive network of stores and online presence, OmniRetail offers a diverse range of products, from electronics to fashion.

Incident Description:
- On April 22, 2024 at 10:00 pm, a state actor (identified as UNC484) gained unauthorized access to OmniRetail’s network.
- The attacker remained undetected for 5 days.
- The initial access was obtained through a critical security vulnerability (CVE-2024-21413) on an external-facing server that the company failed to remediate.
- The attackers targeted specific locations within the network where sensitive data, including Personally Identifiable Information (PII) and Payment Card Information (PCI), was stored.
- Although the databases were properly configured and data was encrypted at rest, one DBA had an unencrypted copy of the data on their O365 OneDrive.
- The file contained PII of approximately 1 million customers (including First Name, Last Name, Email, Home address, Phone, and DOB) from several countries.
- On April 24 (3:00 am), the unauthorized entity copied the file along with an additional 3GB of company proprietary and confidential data to an off-network location.
- On April 26, 2024 (8 pm), the attack was identified when the attackers attempted to deploy Ransomware in the environment.
- The company engaged external legal counsel and a specialized forensics firm for investigation.
- Unauthorized access was revoked, and additional actions included password resets, MFA resets, and server recovery.
- On May 1, 2024 (10:00 am), OmniRetail confirmed unauthorized access to customer data in the environment.
- The ongoing investigation may reveal additional sensitive information exposure, and leaked documents could appear on the Darkweb.
- The company now faces the challenge of navigating compliance requirements and potential legal repercussions across multiple jurisdictions.

Impact:
UK: 160,018
Japan: 956
Singapore: 5,432
US: 833,594 (including 65,021 in California and 150,872 in New York) 1.
