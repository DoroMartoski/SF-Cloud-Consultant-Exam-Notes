# SF-Cloud-Consultant-Exam-Notes - Sharing
Notes from my studies for the SF Sales Cloud consultant exam.
These notes are from my studies in preparation for the Salesforce Sales Cloud Consultant Examination. The notes in some cases may seem rudimentary as this was intended. In studying for every exam - I go into it as someone with no prior knowledge of the matter(I have more than 3 years of Salesforce experience at this time) in order to remove all sorts of knowledge bias. 

Record level security gives users access to some object records but not others High volume customer portal license users - including community and service cloud license users - do not utilize the sharing model. HVCU licenses have their own sharing model that works by foreign key match between the portal user and the data on Account and contact lookups.
HVCU license is only used for the Customer Portal and not the partner Portal.
Chatter free licence doesn't follow the standard sharing model. Chatter free is a collaboration-only license with the following features - chatter, profile, people, groups, files,
Chatter desktop and limited Salesforce 1 app access. **Chatter-free doesn't have access to CRM records (standard or custom) and Content functionality, and therefore there is no sharing.

Org-wide defaults ==> role hierarchy ==> sharing rules ==> manual sharing ==> Team access ==>Territory hierarchy access

Profiles and permission sets provide object-level security by determining what types of data users see and whether they can edit, create oe delete records. **For each object, "View ALl" and "Modify all" permissions ignore sharing rules and settings, allowing admins to quickly grant access to records associated with a given object across the organization.
**These permissions are preferrable alternatives to the "View All Data" and "Modify All Data" admin permissions. Difference between them is that "View ALl" and "Modify All" are for delegation of object permissions for Delegated administrators who manage records for specific objects where as "View All Data" and "Modify ALl Data" are for admin of an entire org.

Users in higher hierarchy(role or territory) inherit the same data access as their subordinates for Standard objects.
Managers gain as much access as their subordinates. This access applies to records owned by users as well as records shared with them.
Queues can be accessed from list views. 
Queues are available for cases, leads, orders, service contracts, knowledge article versions and custom objects.
OWD - are used to lock down(restrict) your data and then use the other record-level security and sharing tools to selectively give access to other users.
OWD are the only way to restrict user access to records.
**If "Grant Access Using Hierarchies" setting under OWD is unchecked - this will prevent managers from inheriting access. 

Role Hierarchy: represents a level of data access that a user or group of users need.
Role hierarchy ensures that managers always have accessto the same data as their employees regardless of the OWD settings.
Each org is allowed 500 roles. Best practice to keep non-portal roles to 25k and portal roles to 100k. ANd 10 role levels.

Uses of role hierarchy include - management access, management reporting, segregation between org branches (different business units don't see each other's data), segregation within role(one can define "leaf" node in which all data is essentially private and still roll that data up to a parent role that can see all).
Ownership-based sharing rules - allow for exceptions to OWD settings and the role hierarchy that give additional user access to records they don't own.
Ownership-based sharing rules are based on the record owner only.** Contact Ownership-based sharing rules don't apply to private contacts.
E.g Share any account owned by a “Western Sales Team” user with any other user that belongs to the “Western Sales Team” role. This means that if Bob is a Western Sales Rep, any accounts that he owns will be available to any of the other Western Sales Team members.

Criteria-based sharing rule: provides access to records based on the record's field values(criteria). Best Practice - keep the number of criteria-sharing rules per object to 50.

Manual sharing - manual sharing is removed when the record owner changes or when the sharing access granted doesn't grant additional access beyond the object's OWD access level.

Team - a group of users that work together on an account, sales opportunity or case. Record owners can build a team for each record that they own and specify access level.

Territory hierarchy - structured by business units or any kind of segmentation in a hierarchical structure.
Territories exist only on Account, opportunity and master-detail.

Implicit sharing - parent implicit sharing(account only). Child implicit sharing - applies to only contact, opportunity or case.

