---
title: Resource Generator
description: Scaffolding files automatically.
---

Building a new feature that requires a database table, a model, and an API endpoint involves a lot of boilerplate code. 

NotifyBay includes a command-line interface (CLI) tool to generate this boilerplate for you instantly.

## Generating a Resource

Open your terminal, navigate to your plugin directory, and run the following command. Replace `<ResourceName>` with the singular, PascalCase name of your resource (e.g., `Product`, `Customer`, `Order`).

```bash
npm run make:resource -- <ResourceName>
```

## What Gets Generated

Assuming you ran `npm run make:resource -- Product`, the CLI will generate the following files:

1.  **Model:** `app/Models/Product.php` - A basic class to handle database operations for this entity.
2.  **Migration:** `app/Database/Migrations/CreateProductsTable.php` - A migration class containing the `CREATE TABLE` SQL statement for `wp_notifybay_products`.
3.  **Controller:** `app/Api/ProductController.php` - A REST API controller with full CRUD endpoints (`GET`, `POST`, `PUT`, `DELETE`).

## Automatic Registration

Not only are the files created, but the CLI also automatically registers them in the appropriate configuration files:

- The Migration is added to `config/migrations.php`.
- The Controller is added to `config/api.php`.

Once you run the command, you can immediately test the API endpoint or navigate to the database to see your new table!

> [!NOTE]  
> See the terminal output screenshot below (once captured) for an example of a successful generation.

<!-- Insert Resource Generator Screenshot Here -->
