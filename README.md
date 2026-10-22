# Open Tracked Profit

_Server variable template for Google Tag Manager (server container)._

The profit of an order: for each product in the event, price times quantity times its margin from your Open Tracked POAS Data Feed. Use it as the conversion value so your ad platforms optimise for profit on ad spend, not revenue. Products without a margin add nothing.

## How to use

1. Switch on **POAS Data Feed** in your Open Tracked dashboard and enter your product margins (or let it take them from your product list). Copy the address and token.
2. Add this variable to your server container and paste the address and token.
3. Use it in an **Augment event** transformation as the `value` of the purchase event for Google Ads, or as `profit` for GA4.

## Fields

| Field | Name | What it does |
|---|---|---|
| POAS Data Feed address | `apiUrl` | From the POAS Data Feed power-up, for example https://app.opentracked.io/api/poas/v1/123. |
| POAS Data Feed token | `token` |  |
| Event data key of the products | `itemsKey` |  |
| When no margin is known, return the event's own value (revenue) | `useRevenueWhenUnknown` | Turn this on where the variable feeds a conversion value: a conversion should never be sent without a value. |

## Privacy

- Only the product IDs of the event are sent to your Open Tracked POAS Data Feed, to read your margins. No visitor data is sent.

## Permissions

- **Reads event data**: Reads the products of the event.
- **Sends HTTP requests**: Only to `https://app.opentracked.io/api/poas/` and `https://app.openserver.digital/api/poas/`.
- **Accesses template storage**: Keeps the margins for a few minutes.

## Notes

Requires an Open Tracked account.

## About Open Tracked

[Open Tracked](https://opentracked.io) is a first-party tracking service: a tagging server on your own domain, an analytics pixel and a CRM. Documentation: https://docs.opentracked.io/google-tag-manager

## License

Apache License 2.0, see [LICENSE](LICENSE).
