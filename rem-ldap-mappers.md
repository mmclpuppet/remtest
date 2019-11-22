---
author: michael.mcloughlin@puppet.com
---

# LDAP mappers

LDAP mappers are listeners, which are triggered by the LDAP Provider at various points, and provide another extension point to LDAP integration.

LDAP mappers are triggered when a user logs in via LDAP and needs to be imported, or when a user is queried from the user admin interface. When you create an LDAP provider, a default set of built-in mappers for this provider is made available. You are free to change this set and create a new mapper, or update/delete existing ones.

|Mapper Type|Description|
|-----------|-----------|
|User Attribute Mapper|This mapper allows you to specify which LDAP attribute is mapped to which user attribute. So, for example, you can configure that LDAP attribute `mail` to the attribute `email` in the Remediate user database. For this mapper implementation, there is always a one-to-one mapping \(one LDAP attribute is mapped to one Remediate user attribute\)|
|FullName Mapper|This mapper allows you to specify that the full name of the user, which is saved in some LDAP attribute \(usually `cn` \), is to be mapped to `firstName` and `lastname` attributes in the Remediate user database. Using `cn` to contain the full name of a user is a common case for some LDAP deployments.|
|Role Mapper|This mapper is not applicable for the current release.|
|Hardcoded Role Mapper|This mapper will grant a specified role to each user linked with LDAP.|
|Group Mapper|This mapper allows you to configure group mappings from LDAP into Remediate user group mappings. A group mapper can be used to map LDAP groups from a particular branch of an LDAP tree into groups in Remediate. It will also propagate user-group mappings from LDAP into user-group mappings in Remediate.|
|MSAD User Account Mapper|This mapper is specific to Microsoft Active Directory \(MSAD\). It can tightly integrate the MSAD user account state into the Remediate user account state \(account enabled, password is expired etc\) using the `userAccountControl` and `pwdLastSet` LDAP attributes \(both of which are specific to MSAD and are not LDAP standard\).|
|Certificate Mapper|This mapper is used specifically for mapping X.509 certificates. It will generally be used in conjunction with X.509 authentication and *Full certificate in PEM* format as an identity source. It behaves the same way as the User Attribute Mapper, but allows you to filter for an LDAP attribute which stores a certificate in either PEM or DER format. It is generally advised to enable **Always Read Value From LDAP** with this mapper.|

**Parent topic:**[Managing user access](managing_user_access.md)

## Adding LDAP mappers

By default, there are User Attribute mappers that map basic Remediate user attributes like `username`, `firstname`, `lastname`, and `email` to corresponding LDAP attributes. You are free to extend these and provide additional attribute mappings.

To add an LDAP mapper:

1.  In the main Remediate UI, click **User admin** on the navigation sidebar.

    The user admin login page is displayed.

2.  Log in with the administrator username and password.

3.  On the sidebar, click **User Federation**, and then click the row assigned to the LDAP/AD connection you want to update.

4.  Click the **Mappers** tab, and then **Create**.

5.  Give the mapper a **Name**, and select the **Mapper Type** from the drop-down list.

6.  Enter the required information in the relevant fields for your mapper type.

    **Tip:** Hover over the ![](Qcircle.png) icon beside each field for more information about the required content for that field.

7.  Click **Save** when you are done.

    **Tip:** To edit your mapper settings, click on the row assigned to it on the **Mappers** tab.


