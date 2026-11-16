# Security

The Movincloud security feature shows the security and compliance status of the inventory assets available on the platform.

To reach the “Security” feature, click the menu icon at the top left: the menu bar opens, where the “Security” entry must be selected. As shown in the figure:

![Opening Security](assets/images/extract/media/image268.png)

The menu of the feature covers the general dashboard, the detail dashboards per resource type (virtual machines, storage, edge devices, network and security with their subtypes), the “Compliance” dashboard, the “Cloud SIEMs” dashboard, the “Key Vaults” dashboard, the “Cluster” dashboard with the cluster alerts and the “Confidential Computing” dashboard.

### General dashboard

On entering the feature, the user lands on the “Dashboard” page, which shows the security data of the resources aggregated across all the configured providers.

At the top is a filter bar that narrows the results by policy name (“Filter by policy name”), “Subsystem” and “Resources Status” (“Healthy”, “Unhealthy”, “Not Applicable”); the two buttons at the right of the bar run the search and clear the filters. The active filters are listed above the bar and can be removed one by one.

Below the filters, three cards summarise the results: the overall compliant state (“Healthy” or “Unhealthy”), the overall resource compliance as a percentage together with the number of healthy resources out of the total, and the number of unhealthy policies.

Next comes the bar chart showing the compliance state of the resources assigned to the policies, broken down by subsystem. Hovering over a section of the chart updates the values in the cards with a preview of the detail; clicking a section of the chart automatically applies the “Subsystem” and “Resources Status” filters to the page.

![Security dashboard](assets/images/extract/media/image269.png)

Under the chart is the policies table, automatically filtered according to the selected filters. For each policy it reports the name, the severity, the subsystem, the user impact, the risks, the compliance state and the number of occurrences.

Next to the table, a doughnut chart reports the distribution of the resources by state: the legend entries show the amount and the percentage of each state and, when clicked, filter the page on that state. The chart button at the top right of the table shows or hides the chart column, to give the table more room.

![Policies table](assets/images/extract/media/image270.png)

Clicking a row of the table opens a detail window with all the information about the selected policy. The lower part of the window lists the resources involved, with the “Show resources which status is:” selector to narrow the list to a single state. Next to each resource a “link” button is available: once clicked, the user is redirected to the Movincloud inventory resource in “view” mode.

![Policy detail](assets/images/extract/media/image271.png)

To leave the detail, click the “X” at the top right of the window or press “Esc”.

### Resource-type dashboards

The policies can be narrowed further by resource type, using the tabs at the top of the page.

Once the resource type is selected, the pages are navigated as described in the previous paragraph.

![Virtual Machine compliance dashboard](assets/images/extract/media/image272.png)

### SIEM dashboard

To view the SIEM dashboard, select the “Cloud SIEMs” entry of the menu. At the top is the filter bar, where the SIEMs of interest and the time range (“1 Day” or “30 Days”) can be selected; the two buttons at the right run the search and clear the filters. The button at the top right of the page offers the “Refresh Analytics” entry, which forces the statistics to be recomputed and reports the outcome with a message.

Below is the “Summary” section, containing the number of alerts, the number of high severity incidents, the total number of incidents with the share of new ones, and the number of total events; the “Summary” section also contains the “Incidents by status” chart, shown when there are incidents; the “Alerts by severity” and “Incidents by severity” charts follow, and can be clicked to filter the page.

Under the “Summary” section, the “Stats” sections report the analytics returned by the SIEM.

![SIEM dashboard](assets/images/extract/media/image273.png)

Scrolling the SIEM dashboard, the charts report the event types detected over the period.

![“Event types" of the SIEM dashboard](assets/images/extract/media/image274.png)

Finally, at the bottom of the page, there are two tables: on the left the “Alert rules” table, which shows a set of alarm rules, and on the right the “Incidents” table, which shows the incidents.

![“Alert rules” and “Incidents” tables](assets/images/extract/media/image275.png)

Clicking a row of the table opens a detail window with all the information about the selected rule or incident.

![“Incidents” detail](assets/images/extract/media/image276.png)

### Key Vaults dashboard

To view the Key Vaults dashboard, select the “Key Vaults” entry of the menu. At the top is the filter bar, where the vault of interest can be selected; the button at the top right of the page offers the “Refresh Analytics” entry.

Under the filters, the collapsible “Summary” panel reports the chart with the totals of the resources held in the selected vault.

![Key Vault dashboard](assets/images/extract/media/image277.png)

Further down, the resources of the vault are organised in tabs:

- “Secrets”
- “Keys”
- “Certificates”
- “Disk Encryption Sets”, shown only when the vault holds some

![Available resources](assets/images/extract/media/image278.png)

Clicking a row of the table shows the detail of the selected resource.

![Key detail](assets/images/extract/media/image279.png)

### Clusters dashboard

The “Cluster” entry of the menu shows, in aggregated form, all the alerts raised by the “Cluster” subsystems configured in Movincloud.

At the top is a filter bar that narrows the results by name (“Filter results”), “Subsystem” and “Namespace”; the two buttons at the right of the bar run the search and clear the filters.

Below the filters, three summary cards report the share of “Info”, “Warning” and “Critical” alerts, each with its count out of the total.

Next, the user sees the bar chart reporting the total number of alerts received, broken down by subsystem. Hovering over a section of the chart updates the values shown in the page with a preview of the detail. A section of the chart can be clicked to apply the “Subsystem” filter automatically.

![“Cluster alerts” dashboard](assets/images/extract/media/image280.png)

Scrolling the page down, there is the “alerts” table, automatically filtered according to the selected filters.

![Alerts table](assets/images/extract/media/image281.png)

Clicking a row of the table opens a detail window with all the information about the selected alert.

To leave the detail, click the “X” at the top right of the window or press “Esc”.

### Compliance dashboard

To view the compliance dashboard, select the “Compliance” entry of the menu.

![Compliance dashboard](assets/images/extract/media/120325001.png)

The page is made of 4 sections.
The first section holds the filters, which allow searching by policy name, subsystem and/or compliance status.
The second section, always active, holds the summary cards with the doughnut charts reporting the overall state of the filtered resources and policies, the overall compliance as a percentage and the number of unhealthy policies.

![“Filters” and “pie charts” sections](assets/images/extract/media/120325002.png)

The third section, active only when the results span more than one subsystem, shows a bar chart of the compliance state of the resources, broken down by provider; here too hovering updates the cards and clicking applies the subsystem filter.
The last section holds a table with the general information about the policy groups: the name, with the icon that tells a policy set from a single policy, the compliance status and, for resources and policies, the percentage of non-compliant ones with the related count.

![“Bar charts” and “table” sections](assets/images/extract/media/120325003.png)

Clicking a row of the table opens a modal where the list of all the policies configured in the group can be seen, with the related resource count; the fields at the top of the modal filter the list by name and by compliance status.
Still inside the modal, one of the listed policies can be clicked; doing so shows, at the bottom, the list of all the machines assigned to the policy and their state.
Next to each resource a “link” button is available; once clicked, the user is redirected to the inventory page of the selected resource.

![Policy detail](assets/images/extract/media/120325004.png)

### Confidential Computing dashboard

To view the confidential computing dashboard, select the “Confidential Computing” entry of the menu. The page lists the instances known to the configured remote attestation servers, together with the state of their memory encryption (SEV).

![Confidential Computing dashboard](assets/images/extract/media/SE001.png)

At the top is the filter bar, where the remote attestation of interest can be selected; the two buttons at the right run the search and clear the filters.

Below the filters, the table reports for each instance its remote attestation, the host name, the KH backend type and the “Security Encryption Verification” state: a closed green padlock means SEV is active, an open red padlock means SEV is not active and a question mark means the state is unknown.

Clicking a row of the table opens a detail window with the general and technical information of the instance (UUID, remote attestation, host name, KH backend type, SEV state, SEV proof, OS version, estimated boot time and boot time), the “Backup Locations”, the last unlock log and the last SEV log.

![Confidential Computing detail](assets/images/extract/media/SE002.png)

To leave the detail, click the “X” at the top right of the window or press “Esc”.
