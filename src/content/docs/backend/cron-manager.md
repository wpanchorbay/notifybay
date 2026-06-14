---
title: Cron Manager
description: Handling background tasks and WP-Cron.
---

WordPress uses WP-Cron to handle scheduled tasks. NotifyBay includes a `Cron.php` manager to simplify the process of registering, scheduling, and executing these background tasks.

## Why Use the Cron Manager?

Manually setting up WP-Cron involves checking if an event is scheduled, adding custom schedules, and hooking into the event. The Cron Manager abstracts this boilerplate, ensuring your jobs are registered correctly and cleaned up when the plugin is deactivated.

## Scheduling Tasks

To add a new background task, you interact with the Cron manager class. It handles registering the schedule (e.g., hourly, daily) and hooking the action to a specific callback method within your plugin.

If you need a custom interval (e.g., every 5 minutes), the Cron Manager can hook into the `cron_schedules` filter to add your custom interval before scheduling the event.

## Executing Tasks

When the scheduled time arrives, WP-Cron will fire the action hook you defined. The method you specified as the callback will then execute in the background.

This is ideal for tasks like:
- Syncing data with a third-party API.
- Cleaning up old logs from the database.
- Processing bulk emails.
