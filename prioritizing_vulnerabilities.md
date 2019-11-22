---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Prioritizing vulnerabilities

To improve your infrastructure security, it is crucial to analyze the vulnerabilities detected during a vulnerability scan. By monitoring the number of vulnerabilities and affected nodes, the risk score, and the analysis of each vulnerability, you can prioritize its remediation and manage your security resources efficiently.

To help you examine the severity of the vulnerabilities in the context of each node, the Vulnerabilities dashboard provides a summary view of the most critical ones detected on your infrastructure.

**Tip:** By default, the dashboard automatically refreshes every 15 minutes. To change to a manual refresh, click **Manage sources** \> **Automatically refresh dashboard**. The manual refresh dashboard option appears at the top of the dashboard.

## Vulnerabilities posing the highest risk to my infrastructure

A risk is a potential for loss, damage, or destruction of a node as a result of a threat exploiting a vulnerability. The risk score assigned to each vulnerability indicates the potential danger it poses to each node. It is based on the impact and possibility of exploit.

The Highest risk vulnerabilities dashboard card highlights the top 3 vulnerabilities detected on your infrastructure that have been assigned the highest risk score.

The Highest risk vulnerabilities page lists and orders vulnerabilities ranked by the assigned risk score and by the number of nodes the vulnerability was detected on.

**Important:** The risk score is assigned by your vulnerability scanner.

## Vulnerable nodes needing immediate attention

A top priority should be to fix a critical vulnerability in a node that’s considered extremely important. However, remediating the same vulnerability might not be a top priority if it’s present on a node of medium or low importance.

The Vulnerable nodes dashboard card highlights the most vulnerable nodes running on your infrastructure that might need immediate attention.

The Vulnerable nodes page lists and orders nodes ranked by the number of vulnerabilities detected on each node.

## Vulnerabilities affecting a large percentage of my infrastructure

The Most common vulnerabilities dashboard card displays the top ten vulnerabilities that have been detected on a large number of nodes running on your infrastructure.

The Most common vulnerabilities page lists and orders vulnerabilities ranked by the number of nodes the vulnerability is detected on.

## Top vulnerabilities requiring remediation

The Top vulnerabilities dashboard card lists the top 5 vulnerabilities detected on nodes running on your infrastructure. The vulnerability is ranked by the risk score assigned to it and the number of nodes it was detected on.

**Important:** The risk scores is calculated using the risk score assigned by your vulnerability scanner multiplied by the number of nodes it was detected on.

-   **[Viewing vulnerability details](viewing_vulnerability_details.md)**  
Use the Vulnerability details page to identify which nodes are affected by the vulnerability, and using the analysis and remediation details determine which task to run on the nodes to help fix the specific vulnerability.
-   **[Filtering and exporting data](filtering_exporting_data.md#)**  
Create custom filters and customize table views to view vulnerability data most important to you, or for backup purposes, export data to a CSV file.

