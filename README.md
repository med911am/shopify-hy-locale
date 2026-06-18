# Shopify Armenian Locale

Armenian (`hy`) locale coverage for Shopify checkout and customer order pages,
built from Shopify's Horizon theme locale structure and Med911's Armenian
storefront work.

## What is included

- `locales/hy.json`: Armenian theme locale JSON with complete
  `shopify.checkout.*` coverage and customer order-history/order-detail strings.
- `storefront/hy.json`: Armenian storefront copy overrides used for Med911
  theme-template content that does not belong in Shopify's locale JSON, such as
  homepage SEO/H1 copy and the custom 404 page.
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

The checkout pack has been reviewed against Shopify's English translation
resource, not only the store's Russian default source. Russian-sourced machine
fills were kept only where they read better in Armenian; high-confidence meaning
drift, brand-name, payment-error, and placeholder-format issues were corrected
from English.

## Usage

Copy `locales/hy.json` into a Shopify theme as:

```text
locales/hy.json
```

Then publish Armenian (`hy`) in Shopify Admin:

```text
Settings -> Languages
```

For storefront template copy, use `storefront/hy.json` as a source map when
registering translations through Shopify Admin API `translationsRegister` for
theme JSON templates or when recreating those blocks in a new theme version.

## Verification

For Med911, the live theme was verified with:

- `shopify.checkout.*` total: 2,564
- missing Armenian checkout keys: 0
- customer order-history/order-detail keys restored: 409
- missing customer order-history/order-detail keys: 0
- final locale leaf keys: 3,374
