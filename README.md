# Pretty Killer Shop

Official merch shop for Finn Shapiro's Pretty Killer Tour.

- **AM (midnight to noon):** the pink **Pretty** side. **PM (noon to midnight):** the black **Killer** side.
- **Testing:** type `am` or `pm` anywhere on the page to switch sides, and `auto` to follow the clock again.
- **Secret code:** typing `movie` puts the Movie in the bag for free (one per bag).
- **Pre-orders:** everything online is a pre-order, so there's no stock limit. People get their items after the show.

## Products

Finn's Choice bundle ($115: K-pop Style CD, hardcover Tour Book, Mini CD Keychain and Mystery Trading Cards, with the Movie free), Tour Book (hardcover, $45), K-pop Style CD, Standard CD, Mini CD Keychain, Sticker Pack, Mystery Trading Cards, Tour Poster, Reversible Bucket Hat (Killer outside, Pretty on the reverse), Digital Album and the Movie. The in-person Good Morning Sun Tee (morning show) and Killer Glow Tee (night show) are shown online but sold only at the merch stand.

## Checkout (Stripe)

**Checkout** sends the whole bag to the [pretty-killer-checkout](../pretty-killer-checkout) server on Vercel (`CONFIG.stripe.checkoutEndpoint`), which makes one Stripe Checkout for everything. The Stripe secret key lives only on Vercel, never in this repo. If `checkoutEndpoint` is empty, Checkout places a test order with no payment.

- Buyers type their **name** in the bag before checking out. Orders are **picked up at the merch stand** (no shipping address).
- After paying they get a **confirmation screen** with their order number (like `PK-4821`), a 2-minute "ready in" timer (`CONFIG.readyAfterMs`) and "Pick it up from the stand".
- **Admin:** `admin.html` lists every paid order with the name, items and total, refreshes every 15 seconds, and has a **Picked up** checkbox (saved on that device). Its password is the `ADMIN_KEY` setting on Vercel, not in this repo.

**Prices are in two places:** `PRODUCTS` here (what people see) and `CATALOG` in the checkout server (what people pay). Change both.

**Photos:** put product photos in `photos/` and list them in `PHOTOS` in `index.html` (the item, then Finn with it, which shows on hover). Items without photos keep their drawn art.

`good-morning-tee.html` is the design sheet for the morning show shirt.
