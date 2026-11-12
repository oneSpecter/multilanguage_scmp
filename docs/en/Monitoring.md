# Monitoring

Movincloud collects metrics from every cloud provider and aggregates them by macro-category, so that metrics coming from different providers can be compared.

The monitoring module is reached from its own menu, which covers the general dashboard, the detail dashboards per resource type (virtual machines, storage, Kubernetes, pods, networks with their subtypes, bastion and firewall), the quotas, the alerts and the reports. As shown in the figure:

![Opening the Monitoring module](assets/images/extract/media/image259.png)

### Monitoring dashboard

The “Dashboard” entry shows an overview of resource usage, broken down by provider and organised by the associated resource type, while the detail entries narrow the view to a single type.

![Monitoring dashboard](assets/images/extract/media/170325001.png)

#### Filters of the Monitoring section

At the top left are the filters on the retrieved resources: provider type, subsystem name and, in the detail dashboards only, resource name. They allow multiple selection and can be combined to reach the desired granularity.

![Monitoring filters](assets/images/extract/media/170325002.png)

### Quotas dashboard

The “Quotas” page shows the consumption and the limits applied to the VCloud subsystems and to the integrated backup systems.

![Opening the Quotas section](assets/images/extract/media/170325003.png)

At the top there is the filter bar, which allows filtering by provider (“Search by provider”), by subsystem (“Search by Subsystem”) and by backup system (“Search by Backup System”); the two buttons at the right of the bar run the search and clear the filters.

Below the filters, the table reports for every subsystem the tenant and the name and, for CPU, memory, storage and backup, the used value, the limit and the usage percentage.

![Quotas dashboard](assets/images/extract/media/170325004.png)

### Alerts on quota usage

The “Alerting” module sends a notification when the quota usage thresholds are exceeded. The page lists the rules configured in the system with their schedule, alert type, send type, creation date, last send date, rule state (“Enabled” or “Disabled”) and the outcome of the last run (“In progress”, “Succeeded” or “Failed”).

![Opening the Alerting system](assets/images/extract/media/090425002.png)

#### Creating a new Alert

The “New rule” button, at the top right, opens the configuration page, organised in three boxes.

![Creating a new Alert](assets/images/extract/media/090425004.png)

In the “Alert configuration” box:

- **“Rule active”**: enables or disables the rule
- **“Alert Type”**: select the type of alert
- **“Quota Type”**: select the quota to monitor, among CPU, memory, storage and backup
- **“Threshold (%)”**: enter the percentage above which the alert is sent
- **“Subsystems”** and **“Backup Systems”**: select the systems to monitor; at least one of the two must be filled in

In the “Schedule configuration” box you set how often the checks run, the date and time of the first run and, unless “Do not set end schedule date” is selected, the end date and time.

In the “Delivery configuration” box:

- **“Alert Send Type”**: select how the alert is received, by e-mail or RabbitMQ (for automatic integration with other systems)
- **“Alert Format”**: select the format of the file carrying the alert details. The field is enabled once the send type has been chosen: “JSON” is always available, “CSV” only with delivery by e-mail
- **“Emails”**: shown only when the alert is sent by e-mail. After typing an address you have to press “Enter” on the keyboard to confirm it: the address moves to the box below and the field is cleared so that a new address can be entered, if needed.

![Configuration page](assets/images/extract/media/090425005.png)

#### Viewing, editing and deleting an Alert

For every rule, the “three dots” button on the right offers the following operations:

- “Show rule” to view the configuration of the rule
- “Edit rule” to change its settings
- “Delete rule” to remove it and stop the notifications
- “Enable rule” and “Disable rule” to suspend or resume the checks without deleting the rule
- “Schedule Now” to run a check immediately
- “Schedule history” to consult the history of the runs

![Operations on the alerts](assets/images/extract/media/090425003.png)

### Reporting tools

The reporting feature, specific to each functional area, makes it possible to generate global reports of the information available for the various providers; inside the pages it is also possible to create files to make sharing that information easier.

To reach the feature, select the “Reports” entry of the Monitoring menu.

![Opening the reporting feature](assets/images/extract/media/MR001.png)

#### Available report types

- **Monitoring Threshold Quotas** – List of the VCloud and/or Backup subsystems integrated in Movincloud, with the detail of the usage quotas (CPU, Memory, Storage, Backup). Depending on the combination of filters selected, the subsystems exceeding a given usage threshold can be filtered.

#### Creating a report

At the top right of the page, the “New report” button starts the creation of a report: a modal is displayed with the list of the available types.

![Creating a new Report](assets/images/extract/media/MR002.png)

Once the type has been selected, click “Configure” to set the filters of the report. The fields required in the “Report data” section depend on the type: for the Monitoring Threshold Quotas they are the provider, the subsystem, the backup system and the usage threshold. If the type provides for a date interval, the “Date range” field appears in the same section for one-shot reports only.

![Configuring the report](assets/images/extract/media/MR003.png)

At this point the user can choose between two different actions:

- creating a static report that will be saved in the system;
- scheduling a recurring generation of the report.

To confirm the creation of a static report, check that “One-Shot” is selected for the “Report Type” field and click the “Submit” button at the bottom. After a loading period the generated report will be visible in the list of the “Ready” tab.

![List of the generated reports](assets/images/extract/media/MR004.png)

##### Scheduling a report

If instead you want the report to run automatically, select “Recurring” for the “Report Type” field: the window is updated to show the additional parameters of the periodic report.

The parameters to enter are:

- “Period”: how often the report is sent (hourly, daily, ...); choosing “Custom” you can enter a Cron expression directly, which is validated by the system
- date and time of the first schedule, with the option to send the first occurrence immediately (“First schedule now”)
- date and time when the schedule ends, or the “Do not set end schedule date” option not to set one
- “Receive only if not empty”: if selected, the file is not sent when it contains no information
- “Report's language”: the language used in the report
- “File format”: one or more file formats to include in the e-mail
- “User E-mails”: the addresses the reports are sent to. After typing an address you have to press “Enter” on the keyboard to confirm it: the address moves to the box below and the field is cleared so that a new address can be entered, if needed

![Parameters of the scheduled report](assets/images/extract/media/MR005.png)

Once all the parameters are configured the “Submit” button becomes clickable: click it to confirm and, after a loading period, the schedule will be visible in the list.

##### List of the scheduled reports

To see the list of the scheduled reports, select the “Scheduled” tab at the top of the reports page.

![List of the scheduled reports](assets/images/extract/media/MR006.png)

This page holds the list and the related information of the scheduled reports present in the system. For each result, clicking the “three dots” button on the right, you can:

- view the last report generated (“Show report”)
- edit the settings of the schedule (“Edit”), without being able to change the selected providers or subsystems
- delete the schedule (“Remove”) to stop the sending of the e-mails
- suspend or resume the sending of the e-mails (“Disable schedule” and “Enable schedule”)

![Editing a schedule](assets/images/extract/media/MR007.png)

##### Using the reports

Clicking the row of a static report, or using the “Show report” button available for the scheduled ones, opens the detail page of the selected report.

At the top are the filters used to generate the report and the date interval of the data; on the right there are the “PRINT” and “EXPORT” buttons. Below is the summary table, paginated; if the report holds too many rows to be displayed in full on screen, a notice invites you to download the file to consult it in its entirety.

Clicking “PRINT” opens the browser print dialog, with a preview of the report. Clicking “EXPORT” the report can be exported as “.csv”, “.json” or “.pdf”.

To go back to the report list, click the “CLOSE” button at the bottom right or the left-pointing arrow at the top, next to the report title.

![Report detail](assets/images/extract/media/image148.png)
