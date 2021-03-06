---
title: Displaying Events in Charts
keywords: events
tags: [events, charts]
sidebar: doc_sidebar
permalink: charts_events_displaying.html
summary: Learn how to display events in charts.
---

When events occur it can be helpful to view them in charts so that you can correlate metric anomalies with the events. Such events include the firing of an alert or the start of a maintenance window. There are also user events, such as deployment activities, that occur outside Wavefront, but can affect the values of metrics. To help you understand the effect of the event on your metrics you can choose whether to display an *overlay* associated with the event on a chart. 

![Events queries](images/events_queries.png)

## Event Overlay Types

If a single event occurs in a given time interval, the event icon displays as a dot on the chart's X-axis. If two or more events occur in a  time interval, the event icon displays as a star on the X-axis. Instantaneous events display a vertical line and non-instantaneous or ongoing events display a shaded region representing the duration of the event. 

![Event overlay](images/event_overlay.png)

The color of the overlays are determined by the event severity:

-   **SEVERE** - red
-   **WARN** - orange
-   **SMOKE** - gray
-   **INFO** - blue

<a name="dashboards_events"></a>

## Controlling Events Overlays

You have several ways to control when event overlays display in charts:

- Select the **Display Source Events** checkbox in the [chart configuration](charts.html#source_events) to display events related to alerts fired for sources displaying in the chart. 

- Add an [events() query](events_queries.html) to the chart. An events() query cannot be the only query on the chart; to display the events at least one ts() query must be enabled on the chart in addition to the events() query.

- For all charts in a dashboard:
  - Set an [events() query](events_queries.html) in [dashboard preferences](dashboards_managing.html#prefs).
  - Select an option in the dashboard **Show Events** dropdown in the middle of the time bar:

    ![time window](images/time_bar.png)
    
    The options are:

    - **From Chart** - Display events based on the selection of the **Display Source Events** checkbox. Default setting.
    - **From Dashboard Prefs** - Display events by the global events() expression set in dashboard preferences and forces the Display Source Events checkbox off.
    - **From Chart & Dashboard**- Display events based on the selection of the Display Source Events checkbox and the global events() expression.
    - **Related Source Alerts** - Forces the Display Source Events checkbox on.
    - **All** - Display all events that have occurred within the time window associated with the chart windows.
    - **None** - Hide all events from every chart in the dashboard.


