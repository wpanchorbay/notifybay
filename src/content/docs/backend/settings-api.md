---
title: Settings API
description: Using the Settings abstraction.
---

Handling plugin options using the native WordPress Settings API can require writing a lot of repetitive HTML and validation code. NotifyBay abstracts this process.

## The Settings Abstraction

Because NotifyBay uses a React frontend for its admin dashboard, the traditional PHP-rendered settings pages (`add_settings_section`, `add_settings_field`) are bypassed for the UI.

Instead, the `Settings.php` class is primarily responsible for:
1. Defining the default values for your options.
2. Providing a structured way to retrieve settings.
3. Validating data before it is saved to the database.

## Schema Validation

When the React frontend sends updated settings via the REST API, the data needs to be validated before being passed to `update_option()`. 

By defining a schema within your settings configuration, you ensure that only the correct data types and allowed values are saved, protecting your database from malicious or malformed input.
