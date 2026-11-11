# Inventory

The inventory feature collects the metadata of the assets installed across all the providers available on Movincloud.

The assets currently supported are:

- Virtual Machine
- Data Stores
- Networks
- Clusters
- Kubernetes
- Edge
- Security
- Others

The heterogeneous metadata coming from the different sources is then normalised by Movincloud to allow a standard presentation.

The inventory is reached from the “Inventory” menu item.

![Opening Inventory](assets/images/extract/media/image104.png)

### Inventory resources

The “Resources” page gives a global, aggregated view of every resource, while the Inventory menu items make it possible to filter by resource type (Virtual Machines, Networks, Clusters, Kubernetes, Data Stores, Security, Edge Devices, Other). The features available in the various pages are identical.

![inventory dashboard](assets/images/extract/media/image105.png)

At the top of the page, next to the title, you find the total number of resources found and three commands:

- “Distribution”, which shows or hides the summary charts;
- “Export”, which exports the current list as CSV, JSON or PDF;
- “Force Sync”, which requests an immediate synchronisation of the resources from the subsystems; a confirmation message appears when it is done.

At the top of the page there is a free-text search field for name, resource group, provider, and so on: pressing “Enter” or the “Search” button refreshes the list. Next to it, the “Filters” button shows the additional filters and reports in a badge how many are active: “Search by tags”, “Search by type”, “Search by provider” and “Search by Subsystem”; choosing a type also brings up its subtypes.

The applied filters are listed as chips at the top of the panel and can be removed one by one or all at once with the crossed-out filter icon button (“Clear”).

![Generic search, by tag, by Provider and Subsystem](assets/images/extract/media/image106.png)

When the charts are visible they show the distribution of the resources by type, by provider, by region and, where the information is available, of the confidential resources. You can also click the charts of types, providers and confidential resources to apply the corresponding filter.

The results table reports provider, name, system name, type and subtype, size, resource group, creation date and state, shown as a coloured tag (green for running resources, red for stopped or failed ones, orange for intermediate states). Three further columns indicate whether the resource is confidential, whether it is a cloud or an on-premise resource and whether it is present in the Movincloud catalogue.

#### Viewing the resource detail

To view the detail of a resource you can either click its table row or use the “Show” option of the “three dots” context menu, as shown below:

![Opening a resource in read mode](assets/images/extract/media/image107.png)

The detail of an asset shows at the top the provider, the name, the state, the subsystem, the last update date and, where available, the “Open in portal” link to the resource on the provider; on the right are the main properties, which depend on the type.

Below is the detail view of a VM:

![Resource detail](assets/images/extract/media/image108.png)

The rest of the page is organised in collapsible panels: “Properties”, “Tags & Notes” and, if the resource has relations, “Relations” and “Relations Chart”.

And at the bottom the relations of the asset with other Movincloud elements, as shown in the figure:

![Relations chart](assets/images/extract/media/image109.png)

The relations chart allows you to navigate between resources by clicking directly on the node of the related resource, so as to land on its detail page. Besides the infrastructure resources, the chart also represents the elements of the Kubernetes clusters (namespaces, deployments, StatefulSets, services, secrets, config maps, volumes, ingresses, network policies, pods and nodes).

Some attributes can also be edited, for example the tags, as shown in the figure:

![Selecting a tag](assets/images/extract/media/image110.png)

In the “Provider tags...” field no tag can be selected, because the tags in this section are retrieved directly from the subsystem

The “Add CMP tag...” field allows you to pick a tag from a list or to type one manually. Each tag carries an “X” symbol to delete it.

Several tags can be added to the resource, together with a free-text note.

Then, at the bottom right of the “Tags & Notes” section, click the “Save” button to save the change; a banner confirms that the tag has been saved.

Scroll to the bottom of the page and click the “Close” button on the right to go back to the resource list; alternatively you can use the back arrow next to the resource title.

#### Actions on inventory machines

For the resources of the supported providers, the “Manage” entry available in the table context menu makes it possible to perform basic operations. The option is available for virtual machines, for virtual networks and for Edge devices.

![Opening the "management" feature](assets/images/extract/media/image111.png)

From this resource detail page the following operations can be performed using the menu at the top of the page; the available operations may vary depending on the provider:

Azure Stack HCI

- Starting the machine
- Stopping the machine
- Resizing the machine
- Disk management: adding a new or existing disk, resizing, detaching and removing (the disk holding the operating system can neither be detached nor removed)
- Network management: adding a network interface, editing the interface (network, subnet, IP address, primary and secondary DNS) and removing it
- Deleting the resource
- Deleting a virtual network: the operation cannot be undone and also removes the attached resources (subnets, network interfaces, ...)

Red Hat Edge

- Updating the image of an EDGE device

Where the environment provides it, the “Manage EDR” operation is also available, which enables EDR on the virtual machine and lets you follow its progress through to completion.

The operations are shown in white when they can be run and in grey when they are not supported or not available for the resource.

![Operations on inventory machines](assets/images/extract/media/image112.png)

#### Virtual machine console

For the virtual machines of the providers that support it, the table menu offers the “Console” entry, which opens the graphical console of the machine.

In the console page the commands “Ctrl+Alt+Del”, “Fit to window”, “Actual size”, “Full screen”, “Reconnect” and “Disconnect” are available. The session closes when you leave the page or after two hours, in which case it is enough to reconnect.

In some environments the “Console” entry offers instead the two modes “noVNC” and “Xterm.js”, which open the console in a new browser window.

#### The “Cluster explorer” feature

The Cluster Explorer is a powerful feature that allows users to inspect in detail the namespaces inside a cluster. It offers a complete overview of how data and resources are organised within the cluster, making it easier to navigate and manage complex environments.

With Cluster Explorer, users can:

- View the full list of the namespaces in a cluster: get a quick overview of all the namespaces available in the cluster.
- Inspect the details of each namespace: access complete information about every namespace, including name, description, labels and resource quotas.
- Filter and search the namespaces: quickly find specific namespaces using advanced filter and search criteria.

To reach the feature, select the “Kubernetes” entry from the Inventory menu, which lists the clusters and the Kubernetes resources present in the configured subsystems. The “Clusters” entry lists instead the clusters of the other providers, for which namespace exploration is not available; the page is split into the “Clusters” and “Nodes” tabs.

![Opening the cluster explorer feature](assets/images/extract/media/image113.png)

The page shows the list of the clusters present in the subsystems configured in the system; clicking one of them opens a modal with the general details of the cluster.

![Cluster detail window](assets/images/extract/media/image114.png)

At the bottom right of the modal there are the “More Details” and “Cluster Explorer” buttons: clicking the latter takes you to the cluster dashboard. The same page can also be reached through the “Cluster Explorer” entry available in the “three dots” context menu of every cluster in the result list.

The page is organised in two tabs, “Overview” and “Explore namespaces”.

In the “Overview” tab you can see the number of namespaces, nodes, pods and running pods, together with a chart representing the distribution of the namespaces within the cluster; on the right the namespace legend is shown with the number of active pods.

![The “cluster explorer” dashboard](assets/images/extract/media/image115.png)

You can drill down into the namespaces using several components of the page:

you can click the “Explore namespaces” button at the top right, or click the number of namespaces shown at the top left, to open the namespace exploration page with no filter; if you want to go straight to the detail of a namespace shown in the chart, you can click its slice and the detail page will be filtered automatically by the selected namespace.

![The "Namespace explorer" page](assets/images/extract/media/image116.png)

The namespaces field at the top allows you to search the available namespaces by free text. If a match is found, the namespace can be selected from the list to view its detail.

![Namespace detail](assets/images/extract/media/image117.png)

The content of the namespace is split into the “Workload”, “Networking”, “Storage” and “Configuration” categories. Using the “down arrow” controls you can navigate the available categories and sub-categories of elements; selecting a result then shows its details in the right-hand section of the page, which is populated automatically with the item selected on the left.

The list of elements can be displayed as “Grid” or as “List”, filtered by name and, when the results are many, extended with the “Show more” button. Where applicable, the right-hand panel also reports the pods assigned to the resource, with access to the detail of the single pod and to the view of its configurations, whose values can be copied.

![Details of the namespace content](assets/images/extract/media/image118.png)

### The “WHAT IF” feature

This feature makes it possible to run simulations for the migration of assets from one provider to another, or within the same provider, so as to compare management and maintenance costs.

To run a simulation, select the ‘What If’ entry from the Inventory menu.

![Opening “What If”](assets/images/extract/media/image119.png)

At the top of the page there are two boxes, one for each type of simulation available: “Migrate to another provider”, to compare current costs with another cloud provider, and “Change resources capacity”, to assess the cost impact of a capacity change.

Further down, the “Previous simulations” section lists the simulations already saved. The two tabs below the title filter the list by simulation type: when the page opens the “Provider Migration” tab is selected, while selecting the “Capacity” tab displays the list of the resource capacity change simulations.

Every simulation reports name, creation date and status, shown with a traffic light: “Saving” when the simulation brings a saving, “Neutral” when costs are equivalent and “Worse” when costs increase. In addition there is the “Destination Providers” column in the “Provider Migration” tab and “Duration” in the “Capacity” one.

![](assets/images/extract/media/image120.png)
![The “What If” page](assets/images/extract/media/image121.png)

#### “What If” scenario: Provider Migration

To run a “What If: Migrate Provider” simulation, click the box titled “Migrate to another provider”

![Opening the "What If: Migrate Provider" feature](assets/images/extract/media/image122.png)

Having done so, the user lands on the “Start” page of step 1 for the simulation of the migration of resources from one cloud provider to another.

On the left, in the “Select Resources to migrate” box, the user can search the resources through three kinds of filter:

- “Search”, which allows you to look for a resource by name;
- “Search by Type”, to obtain the resources by selecting the resource type;
- “Search by tags”, which allows you to search the resources by one or more tags

The resources table only shows resources that have a relation in the catalogue

In the resources table, click one of them and, using the “drag and drop” technique, drag it to the right, into the box titled “Currently selected”.

A maximum of three resources per simulation can be added.

Then, at the bottom right, click the “Next” button.

![Choosing the resources whose provider is to be migrated](assets/images/extract/media/image123.png)

Having done so, the user lands on the “Destination Providers” page of step 2, where one or more providers can be ticked with the checkbox; depending on the type of provider selected, the ‘Option selected” field at the bottom left is filled automatically with the names of the selected providers

Then, at the bottom right, click the “Next” button, while to go back to the “Start” page of step 1 click the “Back” button.

![Choosing the Cloud Provider to migrate the resources to](assets/images/extract/media/image124.png)

After clicking the “Next” button, the user lands on the page of step 3, titled “Details”.

This page shows a set of cards, one for each subsystem selected in step 2.

In every card there is, on the left, a list of the regions available for the cloud provider, while on the right an empty section is shown.

Selecting one or more regions in the left-hand section (in red in the figure) brings up on the right a menu for the cost type (in yellow in the figure): “Consumption” requires no further parameters, “Reservation” allows you to choose the reservation period.

Up to three regions per provider can be selected, as indicated next to the “REGIONS” title; beyond the limit a message is shown. If a provider/region combination is not valid a warning is displayed: the providers highlighted in orange will be excluded from the simulation if you continue.

![Selecting the "Region" and the "Cost Model"](assets/images/extract/media/image125.png)

After clicking the “Next” button, the user lands on step 4, titled “Duration”.

In the “Duration” page of step 4, select an interval for the simulation among:

- “One Month”
- “Six Months”
- “One Year”

To go back to the “Details” page, click the “Back” button at the bottom right. To move on with the simulation, click the “Launch Simulation” button instead.

![Selecting the time interval](assets/images/extract/media/image126.png)

After clicking the “Launch Simulation” button, the user lands on the “Results” page of step 5.

At the top of the “Results” page you can see the “Simulation parameters” box, which contains a summary of the parameters used. (in yellow in the figure)

Below the “Summary” box there are several sections, one per destination provider (in red in the figure); inside each of them you can see the list of the resources that can be migrated to that provider (in green in the figure) and, clicking one of them, a bar chart is displayed. In this chart you can
note:

- A line parallel to the X axis indicating the current cost of the resource.
- A series of bars (one for each selected region and cost type), red when the destination price is higher than the starting one or green when the price is lower than the current cost of the resource; hovering over one of them shows its reference.
- A summary table of the selected cost types, used to build the bar chart, with the estimated costs, the cost difference and the saving percentage.

The details of the other simulations can be viewed (in purple in the figure) with the procedure just described. If the simulation produces no usable result, a dedicated message is shown.

To leave the simulation without saving, click the “Close” button at the bottom right.

To save the simulation, click the “Save” button next to the “Close” button, then click “Confirm”.

After clicking either button, the user is redirected to the “What If” page.

![The WHAT IF simulation results page](assets/images/extract/media/image127.png)

![Summary table of the resource(s)](assets/images/extract/media/image128.png)

A simulation can be updated and run again without re-entering all the data.

To do so, click the row to be changed in the list of the previous simulations; the user is then redirected to step 1 of the simulation, where all the steps have been pre-filled with the saved parameters.

![Starting the update of a "Migrate to another provider" simulation](assets/images/extract/media/image129.png)

#### “What If” scenario: Change Resource Capacity

This feature makes it possible to compare the costs of a resource when its technical characteristics are changed.

Again from the “What If” page, click the “Change resources capacity“ box.

![Opening the "What If: Change resources capacity" feature](assets/images/extract/media/image130.png)

Having done so, the user lands on the “Start” page of step 1

On the left, in the “Select Resources to change” box, the user can search the resources through three kinds of filter:

- “Search”, which allows you to look for a resource by name;
- “Search by Type”, which allows you to obtain the resources by selecting the resource type;
- “Search by tags”, which allows you to search the resources by one or more tags assigned to them.

The resources table only reports resources that, within the Movincloud catalogue, have more than one “Relation” with different sizes but belonging to the same region, the same price type and the same operating system.

At the bottom left there is the resources table, which can be filtered according to the parameters entered in the filter or filters. In the resources table, click one of them and, using the “drag and drop” technique, drag it to the right, into the box titled “Currently selected:”.

A maximum of three resources per simulation can be added.

Then, at the bottom right, click the “Next” button.

![Selecting the resources whose capacity is to be changed](assets/images/extract/media/image131.png)

Having done so, the user lands on the “Resource Provider” page of step 2, where the size of one or more resources can be changed.

In the “Resource Provider” page of step 2, for a given resource, click the drop-down of the “Size” column and select a size different from the initial one among those available, for which the number of CPUs and the RAM are shown. If no alternative size exists for the resource, a dedicated message is displayed.

Then, at the bottom right, click the “Next” button to carry on with the simulation.

To go back to the “Start” page of step 1, click the “Back” button.

![Changing the size of a resource](assets/images/extract/media/image132.png)

After clicking the “Next” button, the user lands on the “Duration” page of step 3.

In that page an interval for the simulation has to be selected.

Then, at the bottom right, click the “Launch Simulation” button.

To go back, click the “Back” button; this takes the user to the “Resource Provider” page of step 2.

![Selecting the interval for the simulation](assets/images/extract/media/image133.png)

After clicking the “Launch Simulation” button, the user lands on the “Results” page of step 4

At the top of the “Results” page there is the “Summary” box, which advises whether to change the size of the resources. Below it there is a bar chart, where the purple bar represents the current costs and the green bar the target costs, followed by the table with the old and the new size, the estimated costs and the saving percentage.

To save the simulation, click the “Save” button next to the “Close” button, then click “Confirm”. The user is then redirected to the “What If” page.

To leave the simulation without saving it, click the “Close” button at the bottom right. The user is then taken to the “What If” page.

![Configuration parameters and advice on the simulation](assets/images/extract/media/image136.png)

#### Exporting a What If scenario

Every saved simulation can be exported as PDF, CSV or JSON; the export is available for both types of simulation.

In the “What If” page, in the “Previous simulations” section, select the tab of the desired type: “Provider Migration” or “Capacity”.

For the simulation to be exported, click the download icon button in the “Export” column.

A sub-menu then opens with the three available formats: “Pdf”, “Csv” and “Json”. Selecting one of them, the file is generated by the system and downloaded automatically.

![Exporting a simulation](assets/images/extract/media/image137.png)

A simulation, of either type, can also be printed.

For a given simulation, click the kebab menu and then click the “Print” option.

A modal with the print preview of the document then appears. Finally, click the “Print” button to start printing the document.

![Printing a simulation](assets/images/extract/media/image138.png)

For a given simulation, click the kebab menu.

From the list of options, click “Delete”.

![Option to delete a simulation](assets/images/extract/media/image139.png)

After clicking the “Delete” option, a modal appears asking you to confirm the deletion of the simulation by clicking the “Yes” button

The simulation is then no longer present in the table.

If you do not want to confirm the deletion of the simulation, click the “No” button.

![Confirming the deletion of a simulation](assets/images/extract/media/image140.png)


### Reporting tools

The reporting feature, specific to each functional area, makes it possible to generate global reports of the information available for the various
providers; inside the pages it is also possible to create files to make sharing that information easier.

To reach the feature, select the “Reports” entry from the Inventory menu

![Opening the Catalogue report](assets/images/extract/media/image141.png)

#### Available report types

- **INVENTORY Summary** – Summary of the quantity of the main inventory resources for the selected provider/subsystem combination.

#### Creating a report

At the top right of the page you can click the “New Report” button to start the creation of a report; a modal is displayed containing the list of the available report types.

![Creating a new report](assets/images/extract/media/image142.png)

Once the report type has been selected, click the “Configure” button to choose the providers to include in the report. In the window that opens there is the “Provider” field, which allows you to select one or more providers already present in the system; then one or more subsystems to include in the report can be selected — if no provider is selected, no subsystem can be chosen. Finally there is a “tag” section to include only the resources carrying the given tag

The fields of the “Report Data” section depend on the report type: for the INVENTORY Summary they are “Provider”, “Subsystem” and “Tags”, plus “Date Range” if the type provides for a date interval. Choosing a predefined time period is available only for recurring reports.

![Configuring the report](assets/images/extract/media/image143.png)

At this point the user can choose between two different actions:

- Creating a static report that will be saved in the system.
- Scheduling a recurring generation of the report.

To confirm the creation of a static report, check that “One-Shot” is selected for the “Report type” field and click the “Submit” button at the bottom.

After a loading period the report just generated can be seen in the list.

![List of the generated reports](assets/images/extract/media/image144.png)

##### Scheduling the report

If instead you want to schedule the automatic execution of the reports, you have to select “Recurring” for the “Report Type” field; the window is then updated to show the additional parameters for configuring the periodic report.

The parameters to enter are:

- Schedule Dates Mode: in the “Report Data” section, it states which data to include in every delivery: a predefined interval (“Time Period”), the last N days (“Last N days”) or fixed dates (“Fixed Dates”).
- Period: allows you to select how often the report is sent (hourly, daily, ...); choosing “Custom” you can enter a Cron expression directly, which is validated by the system.
- Date and time of the first schedule, with the option to send the first occurrence immediately.
- Date and time when the schedule ends, or the option not to set an end date.
- "Receive only if not empty": if selected, the file is not sent when it contains no information
- "Report's language": allows you to select the language used in the report.
- File format: allows you to select one or more file types to include in the e-mail.
- User E-mails: allows you to enter an address the reports are sent to; after typing an address you have to press “Enter” on the keyboard to confirm it — once pressed, the address just entered moves to the box at the bottom and the field is cleared so that, if needed, a new address can be entered.

![Parameters of the scheduled reports](assets/images/extract/media/image145.png)

Once all the parameters have been configured the “Submit” button becomes clickable; click it to confirm and, after a loading period, the report just generated can be seen in the list.

![List of the generated reports](assets/images/extract/media/image144.png)

##### List of the scheduled reports

To see the list of the scheduled reports, select the “Scheduled” tab at the top of the reports page; the “Ready” tab shows instead the reports already generated
.

![List of the scheduled reports](assets/images/extract/media/image146.png)

This page holds the list and the related information of the scheduled reports present in the system. For each result, clicking the “three dots” button on the right, the following operations can be performed:

- Viewing the last report generated.
- Editing the settings of the schedule; the selected providers or subsystems cannot be changed.
- Suspending or resuming the sending of the e-mails, with the “Disable schedule” and “Enable schedule” options.
- Deleting the schedule to stop the sending of the e-mails.

![Editing a schedule](assets/images/extract/media/image147.png)

##### Using the reports

Clicking the row of a static report, or using the “Show report” button available for the scheduled ones, opens the detail page of the selected report.

In the summary of the Inventory report there is a “Stats” section holding the number of disks, interfaces, networks and virtual machines belonging to the selected provider.

Below the “Stats” section there are the filters used to generate the report.

Below the filters there is the summary table of the resources belonging to the providers. On the right there are two buttons: “PRINT” and “EXPORT”. If the report holds too many rows to be displayed in full on screen, a notice invites you to download the file to consult it in its entirety.

Clicking the “PRINT” button, a print preview modal appears. To print the report, click the “Print” button at the bottom right; printing then starts.

Clicking the “EXPORT” button, the report can be exported as “.csv”, “.json” or “.pdf”.

To go back to the report list, click the “CLOSE” button at the bottom right or, at the top left, the left-pointing arrow next to the report title.

![Report details](assets/images/extract/media/image148.png)
