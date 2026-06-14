---
title: REST API
description: How the REST API infrastructure works.
---

The frontend React SPA communicates with the WordPress backend entirely via the REST API. NotifyBay provides a robust infrastructure for creating secure and extendable API endpoints.

## The `ApiController` Abstraction

Instead of registering raw WordPress REST routes using `register_rest_route`, NotifyBay provides a base `ApiController` class.

When you create a new API controller, you extend this base class. This gives you:
- A standardized way to define routes.
- Built-in permission and capability checking.
- Helper methods for sending success or error responses.

### Example Controller

```php
namespace NotifyBay\Api;

class MyCustomController extends ApiController {
    
    // Define the base route
    protected $rest_base = 'custom-endpoint';

    public function register_routes() {
        register_rest_route(
            $this->namespace,
            '/' . $this->rest_base,
            [
                [
                    'methods'             => \WP_REST_Server::READABLE,
                    'callback'            => [ $this, 'get_items' ],
                    'permission_callback' => [ $this, 'get_items_permissions_check' ],
                ]
            ]
        );
    }

    public function get_items( $request ) {
        // Handle logic...
        return rest_ensure_response( [ 'success' => true, 'data' => [] ] );
    }

    public function get_items_permissions_check( $request ) {
        return current_user_can( 'manage_options' );
    }
}
```

## Routing Configuration

Controllers are registered in the configuration files, typically `config/api.php`. This ensures that all controllers are centrally managed and automatically instantiated by the plugin's core router.

## Permissions

Security is paramount. The base architecture encourages you to always provide a `permission_callback` for every route. If you use the Resource Generator CLI, permission checks requiring `manage_options` (admin access) are scaffolded for you by default.
