---
layout: page
title: Author/Co-author Limiter
parent: Platform Customizations
---

**Description**

The platform was customized to keep track of how many papers a user is an author or a co-author on. An ASME admin can set a limit in Extender, per conference (the default limit is 2 papers per user.) When a user hits the limit, they can no longer be assigned to a paper and will be presented with a blocking screen if the assignment is attempted.

---

**Purpose**

ASME has internal policies per conference to limit how many papers a registrant can be a participant on. Previously, this was unevenly enforced by hand. This feature allows them to automate the process.

---

**Requirements**

- The feature is enabled by default on the back-end

---

**Notes**

The feature depends on the cache to show the updated totals, which will update every 15 minutes. Due to this, there are rare cases where an author or co-author can be assigned to a paper more times than what's set as the limit. In these cases, a report is generated from the platform and sent to an ASME admin (currently: Stacey Cooper.) This will allow the admin to manually Disapprove these papers or deal with it on a case-by-case basis.

---

**Troubleshooting**

If ASME reports that the limiter is not working as intended, ask for example submissions first and how many papers a user should be allowed to be assigned to.

   - Check to see if the limit is set according to ASME's preferences in Extender.
   - If the examples fall outside of the range, ask the admin if they have received the report and how many records are included on it.
   - If it's clear that there are more records than would be considered some exceptions, then escalate the issue to the AsmeExtension repo.
