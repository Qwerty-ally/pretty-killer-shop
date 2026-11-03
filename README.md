# Pretty Killer Shop

Official merch shop for Finn Shapiro's Pretty Killer Tour.

- **AM (midnight to noon):** the pink **Pretty** side. **PM (noon to midnight):** the black **Killer** side.
- **Testing:** type `am` or `pm` anywhere on the page to switch sides, and `auto` to follow the clock again.
- **Secret code:** typing `movie` puts the Movie in the bag for free (one per bag).
- **Pre-orders:** everything online is a pre-order, so there's no stock limit. People get their items after the show.

## Products

Finn's Choice bundle ($115: K-pop Style CD, hardcover Tour Book, Mini CD Keychain and Mystery Trading Cards, with the Movie free), Tour Book (hardcover, $45), K-pop Style CD, Standard CD, Mini CD Keychain, Sticker Pack, Mystery Trading Cards, Tour Poster, Reversible Bucket Hat (Killer outside, Pretty on the reverse), Digital Album, Video Pack ($5, music videos and more, with a different Pretty and Killer version) and the Movie. The in-person Good Morning Sun Tee (morning show) and Killer Glow Tee (night show) are shown online but sold only at the merch stand.

## Checkout (Stripe)

**Checkout** sends the whole bag to the [pretty-killer-checkout](../pretty-killer-checkout) server on Vercel (`CONFIG.stripe.checkoutEndpoint`), which makes one Stripe Checkout for everything. The Stripe secret key lives only on Vercel, never in this repo. If `checkoutEndpoint` is empty, Checkout places a test order with no payment.

- Buyers type their **name** in the bag before checking out. Orders are **picked up at the merch stand** (no shipping address).
- After paying they get a **confirmation screen** with their order number (like `PK-4821`), a 2-minute "ready in" timer (`CONFIG.readyAfterMs`) and "Pick it up from the stand".
- **Admin:** `admin.html` lists every paid order with the name, items and total, refreshes every 15 seconds, and has a **Picked up** checkbox (saved on that device). Open it with your private link, `admin.html#<ADMIN_KEY>` (the `ADMIN_KEY` setting on Vercel, not in this repo), and it opens with no password to type. The password box is still there as a backup.

**Prices are in two places:** `PRODUCTS` here (what people see) and `CATALOG` in the checkout server (what people pay). Change both.

**Photos:** put product photos in `photos/` and list them in `PHOTOS` in `index.html` (the item, then Finn with it, which shows on hover). Items without photos keep their drawn art.

`good-morning-tee.html` is the design sheet for the morning show shirt.

## Finn Planning (just for Finn)

`finn-planning-d8b7d0ad.html` is a hidden page (not linked anywhere) with a tab for each item: **K-pop Style CD** (Pretty ver. and Killer ver.) and **Pretty Killer Tour Book**. Each tab lists what comes inside, with a checklist to tick off what's ready (the ticks are saved on that device).

- The K-pop CD tab has a **Photobook** section, from "CD K-pop Final": a start page, then 3 parts, each with an outfit page and 5 songs at 23 pages per song (18 photos, 2 behind the scenes, 1 lyrics page, 1 backstory page, 1 poster). That's 349 pages per version. The 15 song names come from that side of the tracklist.
- Each song's 23 pages follow the grid in `SONG_PAGES`: cover explanation, lyrics, finale, backstory, and photos marked ○ random, □ related to the song, ♡ something with the name.
- The Tour Book is 480 pages (the rest of its contents are still to come).
- The **Shop links** tab has a link to every shop item (Pretty and Killer links for items with two versions) with a Copy button.
- Edit `PRODUCTS` (and `PHOTOBOOK`) at the top of its script.
- The old `kpop-cd-357458f0.html` and `tour-book-dceeeafc.html` links forward to the right tab.

## Product links

`index.html#p-<id>` opens the shop scrolled to that item (for example `#p-hat`), with a pink outline for a few seconds. `#p-<id>-pretty` or `#p-<id>-killer` also shows that side's version for that visit, and the in-person tees switch to the side they're sold on.
