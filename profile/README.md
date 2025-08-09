# Event Tracking

The analytics script supports three types of events:

- Pageviews (automatic)
- Click & Scroll events
- Purchase events

## Installation

Add the analytics script to your website with your site ID:

```html
<script async src="https://script.flowganise.com/?site-id=your-site-id"></script>
```

That's it! The script will automatically start tracking pageviews and provide the `fgan` function for custom events.

## Events

### Pageviews

Pageviews are tracked automatically. You don't need to implement anything specific. The script will:

- Track the initial page load
- Track navigation between pages in single-page applications
- Avoid duplicate tracking on page reloads

### Purchase Events

Track monetary transactions like purchases, subscriptions, or donations.

```javascript
fgan("purchase", {
  currency: "USD",
  value: 30,
});
```

Parameters:

- `currency` (string, required): Three-letter currency code (e.g., "USD", "EUR")
- `value` (number, required): Transaction amount

```

```
