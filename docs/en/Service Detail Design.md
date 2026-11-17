# Service Detail Design

The Service Detail Design service is the solution implemented to manage the requests that then have to be worked, inside our environment, by an authorised user.

To reach Service Detail Design, log in to Movincloud with the Service Manager user, then click the menu icon at the top left and select the “Service Detail Design” entry. As shown in the figure:

![Opening the Service Detail Design module](assets/images/extract/media/image339.png)

The “Work Orders” page opens, where the work orders already created can be filtered. At the top is the filter bar:

- “Select Status…”, which allows more than one status to be selected at a time (“New”, “In progress”, “Idle”, “Rejected”, “Completed”); the “Select All” entry at the head of the list turns every status on or off at once;
- “Select Customer…”;
- “Select a Service Type…”;
- the creation period (“Last 30 days”, “Last 90 days”, “Last year”, “Current year”, “Custom Date”);
- the date range, which shows the dates of the selected period and can be edited only by selecting “Custom Date”.

The table shows the general information of the Work Order.

![Service Detail Design filters](assets/images/extract/media/image340.png)

Click a work order row, anywhere except the “Actions” column, to see its contents; the “Work Order Details” window opens, with the general information at the top and the other sections grouped into panels that expand when clicked. The “Referents” and “Parameters” panels appear only when the request holds them, while “Completion Result” appears only for completed orders.

To leave the detail, click the “X” at the top right of the window or press “Esc”.

![Work Order detail](assets/images/extract/media/image341.png)

### Work Order flow

To take a work order, click the “Resume order” button, the “Play” symbol next to an order in “New” or “Idle” status.

A status change notification is shown and the current status of the Order becomes “In progress”; the buttons of that order change:

- clicking the “Pause order” button moves the order to “Idle” status;
- clicking the “Mark as completed” button closes the Work Order; the button stays visible until the order is closed, but can be used only while the order is “In progress”.

An order already taken can be worked only by the operator who holds it: to every other user, the buttons of that order appear disabled.

![Service Detail Design work order management page](assets/images/extract/media/image342.png)

When the “Mark as completed” button is clicked, the “Close Order” window is shown, where the information to attach to the order can be entered, namely:

- the outcome of the work, which is required;
- a description of the chosen outcome.

![Closing a Work order](assets/images/extract/media/image343.png)

Scrolling the window down, there is the “Delivery Data” section.

Further parameters can be entered as key/value pairs in the row at the bottom, then click the “Plus” button to confirm; to remove a pair that was added, click the “Minus” button.

Once every parameter is entered, click the “Finish” button: the order moves to “Completed” status.

![Entering parameters](assets/images/extract/media/image344.png)

Once the order is completed, the detail can be opened again to see the information entered during the work.

![Information added during the work](assets/images/extract/media/image345.png)
