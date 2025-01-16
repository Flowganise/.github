# Event Tracking

The analytics script supports three types of events:

- Pageviews (automatic)
- Custom events
- Transaction events

## Installation

Add the analytics script to your website and initialize it with your organization ID:

```html
<script async src="https://script.flowganise.com/"></script>
<script>
  window.flowganise = window.flowganise || [];
  function fgan() {
    flowganise.push(arguments);
  }
  fgan("js", new Date());
  fgan("config", "your-organization-id");
</script>
```

## Events

### Pageviews

Pageviews are tracked automatically. You don't need to implement anything specific. The script will:

- Track the initial page load
- Track navigation between pages in single-page applications
- Avoid duplicate tracking on page reloads

### Custom Events

Track user interactions like button clicks, link clicks, or any other clickable elements.

```javascript
fgan("custom", label, metadata?)
```

Parameters:

- `label` (string, required): Identifier for the click event
- `metadata` (object, optional): Additional information about the click

Examples:

```javascript
// Basic click tracking
fgan("custom", "signup-button");

// Click with location metadata
fgan("custom", "download-pdf", {
  location: "header",
  fileName: "user-guide.pdf",
});

// Navigation custom
fgan("custom", "menu-item", {
  section: "main-menu",
  destination: "pricing",
});
```

### Transaction Events

Track monetary transactions like purchases, subscriptions, or donations.

```javascript
fgan("transaction", currency, value, label, metadata?)
```

Parameters:

- `currency` (string, required): Three-letter currency code (e.g., "USD", "EUR")
- `value` (number, required): Transaction amount
- `label` (string, required): Identifier for the transaction
- `metadata` (object, optional): Additional transaction details

Examples:

```javascript
// Basic purchase
fgan("transaction", "USD", 99.99, "pro-subscription");

// Product purchase with details
fgan("transaction", "EUR", 49.99, "product-purchase", {
  productId: "widget-123",
  quantity: 1,
});

// Subscription with plan details
fgan("transaction", "USD", 199.99, "annual-plan", {
  plan: "enterprise",
  term: "yearly",
});
```
