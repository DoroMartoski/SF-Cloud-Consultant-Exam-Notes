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

<b>Currencies in Salesforce:</b>

Corporate currency: Bases for all currency conversion rates in your org - it's also the currency your org's corporate HQ reports revenue in.

Conversion Rates: this is the currency conversion rates between the corporate currency and the multiple currencies used by your organization. Maintained by your admin.

Personal currency: a user's default currency for quotas, certain forecasting versions and reports. Must be one of the active currencies for your org. ** Your quota amounts display in your display currency if using Collaboarative Forecasts.

Active Currency: a currency in which your org does business. Only active currencies can be entered in opportunities, forecasts and other items.

Inactive currency: a currency that your organization no longer uses. **You may have existing records that uses inactive currencies but you can't enter new amounts using inactive currencies.

Record currency: the default currency for a record. Every record has a currency field that specifies the currencytype for amounts in that record.

Roll up summaries will not work between an object that is enabled for advanced currency management and one that is not. E.g opportunity and custom object but will work for opportunity and opportunity line item.


** Opportunity amounts display in the record currency as well as the opportunity owner's personal currency.

All currency amounts display in the record's currency and also converted to the personal currency(displayed in parenthesis) of the record owner based on conversion rates entered by admin.

<b>In Quotas</b>, by default your quota amounts display in your personal currency but you can change to any of your org's active currency.
** If using Collaborative forecast then your quota displays in your display currency.

<b>In forecasts</b> admins set up forecasts for an organization and chooses a forecast currency and enable one or more types of forecasts. The forecast currency is either the organization's corporate currency or each forecast owner's personal currency.

<b>In Reports</b> amounts in reports are shown in their original currencies but can be displayed in any active currency(show ==> currencies).
**Default value for currency reporting is your personal currency. You can choose to display the converted column - e.g Annual Revenue converted - which shows amounts in the currency you select.

<b>In list view Criteria and report filters</b> to limit your data to items with specific currencies or amounts, prefix currency amounts with currency code - USD for dollars.
**All amounts are converted to the corporate currency for comparison.
**Without currency code all amounts are assumed to be in the user's personal currency.

**If you change the start month of your organization’s fiscal year, the fiscal quarters shift and different months are regrouped into new
quarters. This can change the forecast currency for each quarter. The new forecast currency for each quarter becomes the currency of
the third month in that quarter.
