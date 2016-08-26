# SF-Cloud-Consultant-Exam-Notes
Notes from my studies for the SF Sales Cloud consultant exam.

Record level security gives users access to some object records but not others High volume customer portal license users - including community and service cloud license users - do not utilize the sharing model. HVCU licenses have their own sharing model that works by foreign key match between the portal user and the data on Account and contact lookups.
HVCU license is only used for the Customer Portal and not the partner Portal.
Chatter free licence doesn't follow the standard sharing model. Chatter free is a collaboration-only license with the following features - chatter, profile, people, groups, files,
Chatter desktop and limited Salesforce 1 app access. **Chatter-free doesn't have access to CRM records (standard or custom) and Content functionality, and therefore there is no sharing.

Org-wide defaults ==> role hierarchy ==> sharing rules ==> manual sharing ==> Team access ==>Territory hierarchy access

Profiles and permission sets provide object-level security by determining what types of data users see and whether they can edit, create oe delete records. **For each object, "View ALl" and "Modify all" permissions ignore sharing rules and settings, allowing admins to quickly grant access to records associated with a given object across the organization.
**These permissions are preferrable alternatives to the "View All Data" and "Modify All Data" admin permissions. Difference between them is that "View ALl" and "Modify All" are for delegation of object permissions for Delegated administrators who manage records for specific objects where as "View All Data" and "Modify ALl Data" are for admin of an entire org.

