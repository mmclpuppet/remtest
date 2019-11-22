---
author: michael.mcloughlin@puppet.com
---

# Remediate your top vulnerabilities

The **Top vulnerabilities** table on the Vulnerabilities page lists the vulnerabilities that you need to address most urgently. The ranking on this table is based on a combination of risk score and number of network nodes affected.

To remediate a top vulnerability:

1.  On the Vulnerabilities page, click the vulnerability you want to address on the **Top vulnerabilities** table.

2.  On the Vulnerability detail page, review the analysis and remediation information that is displayed for the selected vulnerability.

    -   The **Analysis** section provides you with information on the nature of the vulnerability and the threat it poses.
    -   The **Remediation** section gives practical information on the remediation task you need to carry out to block the threat \(where provided by your vulnerability scanner\).
3.  In the **Nodes affected** table, select the nodes to which you want the remediation task to apply.

    **Note:**

    If Remediate does not have the credentials to apply a task to a node, it is not selectable in the **Nodes affected** table.

4.  Click **Run Task** and select the appropriate task type from the drop-down list.

5.  On the Configure task page, configure the task as required. Instructions on remediation for the selected vulnerability are visible on this page. Click **Review Nodes** when you are done.

6.  On the Review nodes page, ensure that all the nodes to which you want to apply the task are selected. When ready, click **Select credentials**.

7.  On the Select credentials page, select the credentials that allow you to run the task on the selected nodes, and click **Review task summary**.

8.  On the Review and run task page, verify that the task summary information is correct, and click **Run task**.

    A confirmation message appears at the top of the page, confirming that the task type that is now running and how many nodes it affects..

    **Note:** The changes made by the task if successful will only be reflected here after your next security scan, so don’t worry if you see no updates at this point.


**Parent topic:**[Remediating vulnerabilities](remediating_vulnerabilities.md)

