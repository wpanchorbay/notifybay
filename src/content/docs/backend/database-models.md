---
title: Database & Models
description: Managing custom database tables and data models.
---

For complex plugins, relying solely on `wp_options` or `wp_postmeta` is often inefficient. NotifyBay provides a clean way to manage custom database tables and the models that interact with them.

## Database Manager (`DbManager.php`)

The plugin uses a Database Manager to handle the creation and updating of custom tables via the native WordPress `dbDelta()` function.

### Migrations

Schema changes are defined in migration classes. When you need a new table, you create a migration file that specifies the SQL schema.

Migrations are registered in `config/migrations.php`. When the plugin is activated or updated, the `DbManager` runs through the registered migrations and applies any necessary schema changes.

## Models

Models are PHP classes that represent a row (or collection of rows) in your database. They abstract the raw SQL queries, providing a clean object-oriented interface for CRUD (Create, Read, Update, Delete) operations.

While NotifyBay doesn't use a full ORM like Eloquent, its Models provide a structured way to interact with the `$wpdb` global.

### Creating a Model

Instead of writing SQL everywhere in your API controllers, you should encapsulate that logic within a Model.

```php
namespace NotifyBay\Models;

class CustomItem {
    
    public static function get_all() {
        global $wpdb;
        $table_name = $wpdb->prefix . 'notifybay_custom_items';
        return $wpdb->get_results( "SELECT * FROM $table_name" );
    }

    public static function create( $data ) {
        global $wpdb;
        $table_name = $wpdb->prefix . 'notifybay_custom_items';
        $wpdb->insert( $table_name, $data );
        return $wpdb->insert_id;
    }
}
```

> [!TIP]  
> The fastest way to create a Model, its Migration, and its API Controller is by using the [Resource Generator CLI](../guides/resource-generator).
