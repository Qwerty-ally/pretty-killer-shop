# Pretty Killer Shop

Official merch shop for Finn Shapiro's Pretty Killer Tour.

- **AM (midnight to noon):** the pink **Pretty** side. **PM (noon to midnight):** the black **Killer** side.
- **Testing:** type `am` or `pm` anywhere on the page to switch sides, and `auto` to follow the clock again.
- **Secret code:** typing `movie` puts the Movie in the bag for free (one per bag).
- **Admin:** click **Admin** in the footer. The test PIN is `1234` (`CONFIG.adminPin`).

## Products

Finn's Choice bundle, Tour Book, K-pop Style CD, Standard CD, Mini CD Keychain, Sticker Pack, Mystery Trading Cards, Tour Poster, Bucket Hat, Hair Clip Set, Digital Album and the Movie. The in-person Good Morning Sun Tee (morning show) and Killer Glow Tee (night show) are shown online but sold only at the merch stand.

## Still to connect

- **Firebase** (`CONFIG.firebase` and the `TODO(firebase)` notes in the script): stock is saved in each visitor's browser until it's connected.
- **Stripe** (`CONFIG.stripe` and the `TODO(stripe)` notes): checkout places a test order until it's connected. Only the publishable key goes in the page, never the secret key.

`good-morning-tee.html` is the design sheet for the morning show shirt.
