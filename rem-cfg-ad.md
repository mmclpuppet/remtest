---
author: michael.mcloughlin@puppet.com
---

# Active Directory configuration

You can set up Remediate to use Active Directory to authenticate users.

To configure Remediate to use your Active Directory server:

1.  In the main Remediate UI, click **User admin** on the navigation sidebar.

    The user admin login page is displayed.

2.  Log in with the administrator username and password.

3.  On the sidebar, click **User Federation** and select *ldap* from the drop-down list.

4.  In the **Required Settings** area:

    1.  Select *Active Directory* from the **vendor** drop-down list.

        **Note:** Some of the required parameters will be automatically filled. These parameters can be changed if they are unsuitable.

        Hover over the ![](Qcircle.png) icon beside each field for more information about the required content for that field.

    2.  Enter the **Username LDAP Attribute**.

    3.  Enter the **RDN LDAP Attribute**.

        This is the attribute that defines the relative distinguished name of the typical user distinguished name. Usually, it is the same as the username attribute. However, you might also use `cn` for this attribute if you used sAMAccountName for the username attribute.

    4.  Enter the **UUID LDAP attribute**.

        For Active Directory, this is usually `objectGUID`.

    5.  Enter values for all LDAP **User Object Classes**. Values must be comma-separated, for example:

        ```
        InetOrgPerson,organizationPerson
        ```

    6.  Enter the **Connection URL** of your LDAP server.

        For example:

        ```
        ldap://ds.example.com:389
        ```

        Or:

        ```
        ldaps://ds.example.com:636
        ```

        You can use the **Test connection** button to ensure that Remediate can connect to the server.

    7.  Enter the **User DN**.

        The is the full distinguished name of the LDAP tree where your users are located. For example:

        ```
        ou=Users,dc=remediate,dc=io
        ```

    8.  Select the **Authentication Type**. There are two options:

        -   *None* - anonymous LDAP authentication.
        -   *Simple* - Bind credential + Bind password authentication.
    9.  Enter the **Bind DN** field. This is the distinguished name of the LDAP admin account used to access the LDAP server. For example:

        ```
        cn=admin,dc=remediate,dc=io
        ```

    10. Enter the LDAP admin password in the **Bind Credential** field.

        You can use the **Test authentication** button to see if Remediate can access the LDAP server.

5.  To configure the synchronization schedule between your LDAP or Active Directory server and Remediate:

    1.  Enter the maximum number of users to be imported in any transaction in the **Batch Size** field. The default is *1000*.

    2.  If you want to set up a full synchronization, set **Periodic Full Sync** to *ON*, and enter a value in seconds in the **Full Sync Period** field. The default is *604800* seconds \(every 7 days\).

    3.  If you want to synchronize only new and changed users, set **Periodic Changed Users Sync** to *ON* and enter a value in seconds in the **Changed Users Sync Period** field. The default is *86400* seconds \(every 24 hours\).

6.  When you are done, click **Save**.


**Parent topic:**[Managing user access](managing_user_access.md)

**Related information**  


[LDAP mappers](rem-ldap-mappers.md#)

