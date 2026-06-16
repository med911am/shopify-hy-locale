# Shopify Armenian Locale

Armenian (`hy`) locale coverage for Shopify checkout and customer order pages,
built from Shopify's Horizon theme locale structure and Med911's Armenian
storefront work.

## What is included

- `locales/hy.json`: Armenian theme locale JSON with complete
  `shopify.checkout.*` coverage and customer order-history/order-detail strings.
- All 2,564 checkout translation keys present in Shopify's
  `ONLINE_STORE_THEME_LOCALE_CONTENT` resource are present in the locale file.
- `customer_accounts.orders.*` and `customer_accounts.order_details.*` are
  included for customer account order history and order detail pages.
- Liquid/Shopify placeholders such as `%{amount}`, `%{code}`, and
  `{{ count }}` are preserved.

## Notes

Shopify currently rejects locale assets above roughly 3,400 leaf translation
keys. To keep complete checkout plus order-history coverage under that cap, this
pack prioritizes the storefront, checkout purchase flow, and customer order
pages over lower-priority B2B, payment-method-management, blog, gift-card, and
generic system notice strings.

Some long-tail checkout error strings were machine-translated from Russian and
validated for placeholder preservation. Human review is recommended before
using this as a canonical public localization.

## Usage

Copy `locales/hy.json` into a Shopify theme as:

```text
locales/hy.json
```

Then publish Armenian (`hy`) in Shopify Admin:

```text
Settings -> Languages
```

## Verification

For Med911, the live theme was verified with:

- `shopify.checkout.*` total: 2,564
- missing Armenian checkout keys: 0
- customer order-history/order-detail keys restored: 409
- missing customer order-history/order-detail keys: 0
- final locale leaf keys: 3,360
