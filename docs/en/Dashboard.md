# Dashboard

When you log in to Movincloud, the “Overview” homepage presents a summary of the four areas of the platform: inventory, costs, security and monitoring. Only the areas the user has permissions for are shown.

Below the title, a bar of links (“Inventory”, “Costs”, “Security”, “Monitoring”) jumps straight to the corresponding section of the page.

The “Key indicators” section summarises the four areas in as many cards: the total number of resources, the total costs, the compliance percentage with the number of compliant assessments, and the average CPU usage.

In detail:

- The “Inventory” section shows a donut chart of the resources by type, with the total in the middle and, in the legend, the count and the percentage of every type; below it, “Resources by provider” reports one card per provider with the distribution of its resources and its most frequent type.
- The “Costs” section shows the recalculated value for the period and, for the users who see full costs, also the total, the forecast and the difference between recalculated and total; the “Cost trend” chart with daily and cumulative costs follows.
- The “Security” section shows a donut chart of the assessment outcomes (“Compliant”, “Non-compliant”, “Not applicable”) and a card with the overall compliance percentage; below it, “Assessments by provider” reports the outcomes provider by provider.
- The “Monitoring” section shows the metrics of the selected tenant, computed as an average over the last five hours: CPU, memory, storage, network packets, vGateway, K8S, bastion and firewall. Metrics with no samples in the period report “No data”. The “Show Grafana panels” button opens the Grafana panels with the operational status, which can be collapsed again with “Hide Grafana panels”.

![Dashboard "Inventory" section](assets/images/extract/media/image100.png)

![Dashboard "Monitoring" section](assets/images/extract/media/image101.png)

![Dashboard "Costs" section](assets/images/extract/media/image102.png)

![Dashboard "Security" section](assets/images/extract/media/image103.png)
