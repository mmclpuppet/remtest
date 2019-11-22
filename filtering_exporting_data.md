---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Filtering and exporting data

Create custom filters and customize table views to view vulnerability data most important to you, or for backup purposes, export data to a CSV file.

**Parent topic:**[Prioritizing vulnerabilities](prioritizing_vulnerabilities.md)

## Create custom filters

You can create a list of nodes or vulnerabilities for further investigation by creating a custom filter with multiple criteria.

1.  On any listing or details page, click **Create filter**.

2.  Select a **Field**.

3.  Select an **Operator**:

    |Operator|Filter for resources where the value of the field:|
    |--------|--------------------------------------------------|
    |**Equals**|is an exact match to the value you specify.|
    |**Not equal to**|is anything except an exact match to the value you specify.|
    |**Contains**|contains the value you specify.|
    |**Does not contain**|does not contain the value you specify.|

4.  Enter a **Value**.

5.  Click **Add filter**.

6.  To add criteria to the filter, click **Add another filter**.

7.  As needed, repeat these steps to add additional filters.

8.  To display the filtered list, click **Apply all**.


## Customize table views

Customize each table view by showing or hiding table columns on any of the node or vulnerability pages.

1.  On any listings or details page, click **Columns +/-**.

    By default, all available table columns are selected.

2.  To hide a table column, click the column header to remove the selection indicator \(![](tick_icon.png)\).

3.  To confirm your selections, click **Apply**.


## Export data

To keep a backup of data relating to nodes or vulnerabilities, download a CSV file that contains the same information as the page you are currently viewing, including all filter selections.

To download resource data as a `.csv` file, click **Export**. The filename is `<ui_page>_<timestamp>.csv`, for example `pd_export_highest_risk_vulnerabilities_2019-06-17_1054.csv`.

