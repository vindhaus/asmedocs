---
layout: page
title: Automatic Author/Co-Author Disapproval
parent: Platform Customizations
---

**Description**

A daily automated job will check if any submissions contain authors or co-authors who do not have an SSO ID in their profile. 8 days from when the submission was created, if any of the authors or co-authors still do not have an SSO ID in their profile, the entire submission is automatically marked as Disapproved.

---

**Purpose**

In order for an author or co-author to register for ASME's conferences, they must login to OpenWater first to acknowledge their participation and consent on the submission. Disapproving their papers is a way for ASME to ensure that papers are filtered out, which do not contain this acknowledgment by all authors listed on the paper.

---

**Requirements**

- The OFAC job in Extender must be enabled, per conference.

---

**Troubleshooting**

If ASME reports that submissions are not being Disapproved as they expect, ask for example submissions first.

   - Check all of the authors on the submission to see if any of them are missing an SSO ID in their user profile
      - If they all have SSO IDs, then the job is working as intended
      - If the paper's submission date is less than 8 days from the time of investigation, then the job is working as intended

   - If one of the authors has no SSO ID and it's been 8 days since the paper's submission date
      - Check to see if the OFAC job is enabled in Extender for the conference in question. If it is not enabled, then enable it and let ASME know they will have to manually Disapprove all papers that were submitted prior to the job's enablement.
      - If the OFAC job is enabled, check Hangfire to see if it has failed. If so, escalate to the AsmeExtension repo in Github. Include a link to the failed job error. Also include the example submission, the day it was submitted and which author has a missing SSO ID.
      - If no Hangfire error is found, escalate to the AsmeExtension repo in Github with the example submission. Note its day of submission in the ticket and which author has a missing SSO ID.
