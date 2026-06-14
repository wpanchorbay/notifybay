---
title: Adding Admin Pages
description: How to create a new page in the React dashboard.
---

Because NotifyBay uses a React SPA architecture, adding a new page to the admin dashboard involves creating a React component and registering it with the router, rather than creating a new PHP file.

## Step 1: Create the Component

First, create a new file in `src/pages/`. Let's say you want to create a "Reports" page.

Create `src/pages/Reports.tsx`:

```tsx
import React from 'react';

const Reports: React.FC = () => {
    return (
        <div className="notifybay-ignore-preflight">
            <h2>Reports Dashboard</h2>
            <p>This is the new reports page.</p>
        </div>
    );
};

export default Reports;
```

## Step 2: Register the Route

Next, open `src/App.tsx`. You need to import your new component and add a `Route` inside the `Routes` block.

```tsx
// Inside src/App.tsx
import Reports from './pages/Reports';

// Inside the <Routes> component:
<Route path="/reports" element={<Reports />} />
```

## Step 3: Add to Navigation

Finally, you need to provide a way for the user to navigate to this page. You can add a link to the main sidebar or navigation menu (depending on whether you are using the `ClassicLayout` or `AppLayout`).

Use the `Link` component from `react-router-dom`:

```tsx
import { Link } from 'react-router-dom';

<Link to="/reports">View Reports</Link>
```

> [!NOTE]  
> See the screenshot below (once captured) to see how the new page looks in the dashboard.

<!-- Insert New Admin Page Screenshot Here -->
