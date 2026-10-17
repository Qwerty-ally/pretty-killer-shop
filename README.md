# Pretty Killer Shop

Official merch shop for Finn Shapiro's Pretty Killer Tour.

- **AM (midnight to noon):** the pink **Pretty** side. **PM (noon to midnight):** the black **Killer** side.
- **Testing:** type `am` or `pm` anywhere on the page to switch sides, and `auto` to follow the clock again.
- **Secret code:** typing `movie` puts the Movie in the bag for free (one per bag).
- **Pre-orders:** everything online is a pre-order, so there's no stock limit. People get their items after the show.

## Products

Finn's Choice bundle ($101: K-pop Style CD, hardcover Tour Book, Mini CD Keychain and Mystery Trading Cards, with the Movie free), Tour Book (hardcover $45 or paperback $37), K-pop Style CD, Standard CD, Mini CD Keychain, Sticker Pack, Mystery Trading Cards, Tour Poster, Bucket Hat, Hair Clip Set, Digital Album and the Movie. The in-person Good Morning Sun Tee (morning show) and Killer Glow Tee (night show) are shown online but sold only at the merch stand.

## Checkout (Stripe)

**Checkout** sends the whole bag to the [pretty-killer-checkout](../pretty-killer-checkout) server on Vercel (`CONFIG.stripe.checkoutEndpoint`), which makes one Stripe Checkout for everything. The Stripe secret key lives only on Vercel, never in this repo. If `checkoutEndpoint` is empty, Checkout places a test order with no payment.

**Prices are in two places:** `PRODUCTS` here (what people see) and `CATALOG` in the checkout server (what people pay). Change both.

`good-morning-tee.html` is the design sheet for the morning show shirt.
