---
title: Logger
description: Database-based logging in NotifyBay.
---

When developing complex plugins or integrating with external APIs, relying solely on `error_log` is often insufficient. NotifyBay includes a custom database-based Logger.

## The `Logger.php` Class

The Logger class allows you to write structured log entries directly to a custom database table. This is incredibly useful for tracking background tasks, API sync errors, or complex state changes that you want to review later via the admin interface.

## Log Levels & Context

The Logger supports standard severity levels (e.g., `info`, `warning`, `error`, `debug`).

### Adding Context

Instead of concatenating massive strings, the Logger accepts an array of context data. This data is stored as a JSON object in the database.

```php
use NotifyBay\Helper\Logger;

// Example of logging an API error with context
Logger::error( 'Failed to sync user data', [
    'user_id' => 123,
    'api_response_code' => 500,
    'endpoint' => '/v1/users/sync'
] );
```

This JSON context can then be easily parsed and displayed in a structured format within the React admin dashboard, making debugging much easier.
