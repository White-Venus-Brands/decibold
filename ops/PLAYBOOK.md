# Decibold — Instagram & store operations playbook

Read this first in every scheduled run. Source of truth for how the Decibold
marketing automation works. Owner: Tannay. Sister setup: Mi Amor Paris
(`White-Venus-Brands/miamorparis-assets`) — never mix the two brands' accounts.

## Accounts and IDs
- Instagram: @TBD — Business account, linked to the Decibold Facebook Page. (TBD: handle)
- Facebook Page: TBD.
- Shopify store: `t0m8zb-vw.myshopify.com`, public site https://www.decibold.com, INR.
- Metricool brand: "Decibold", brandId TBD (find with getBrandSettings; NEVER use 7658526, that is Mi Amor Paris).
- Meta ad account: TBD (Adspirer). NEVER touch SSMK-Mi Amor Paris 1367716178225422.
- Image hosting: this repo, commit-pinned raw URLs:
  `https://raw.githubusercontent.com/White-Venus-Brands/decibold/<commit-sha>/<path>`

## Which tool does what
- **Posting: Metricool** (brand "Decibold") via createScheduledPost with commit-pinned raw URLs.
- **Live prices and product facts:** WebFetch `https://www.decibold.com/products.json`
  (public, no login). Use `price` and `compare_at_price` from there at the moment of posting.
- **Shopify connector stays on the Mi Amor Paris store.** Do NOT call switch-shop from a
  Decibold run: it revokes Mi Amor Paris access and breaks its daily scheduled tasks.
  Decibold sales/orders reports: TBD (Zapier Shopify connection for Decibold, once Zapier is upgraded).
- Instagram stats: Metricool getAnalyticsDataByMetrics with the Decibold brandId.
- Keyword comments/DMs: ManyChat (Decibold workspace). Never turn on Metricool auto-replies.
- WhatsApp: Decibold WhatsApp Business number with its own AI (not run by Claude).

## Catalog (from decibold.com/products.json, 30 Oct 2026 — always re-check prices live)
| Product | Handle | Price | Was |
|---|---|---|---|
| db201 80W 2.1 Soundbar | decibold-db201-80w-2-1-channel-soundbar | ₹14,999 | ₹24,999 |
| db302 50W 2.0 Bookshelf Speakers | decibold-db302-50w-2-0-bookshelf-speakers | ₹9,999 | ₹14,999 |
| db403 100W 2.0 Bookshelf Speakers | decibold-db403-100w-2-0-bookshelf-speakers | ₹16,999 | ₹24,999 |
| 8" 100W Active Subwoofer | decibold-8-inch-100w-active-subwoofer | ₹14,999 | ₹24,999 |
| 10" 150W Active Subwoofer | decibold-10-inch-150w-active-subwoofer | ₹19,999 | ₹34,999 |
| db403 + 8" sub combo (2.1) | decibold-db403-100w-bookshelf-speakers-8-inch-100w-active-subwoofer-combo-2-1-home-audio-system | ₹29,999 | ₹49,999 |
| db403 + 10" sub combo (2.1) | decibold-db403-100w-bookshelf-speakers-10-inch-150w-active-subwoofer-combo-2-1-home-audio-system | ₹34,999 | ₹59,999 |
| Speaker Stand (1 pair) | decibold-speaker-stand-1-pair | ₹1,999 | ₹2,999 |

Setups (from the website): The desk = db302 alone; The living room = db201 + 10" sub
(larger room) or db302 + 8" sub (smaller room); The studio = db403 + a subwoofer;
The full room = db403 + 10" sub.

## Hard rules
1. **Posting autonomy: NOT granted yet for Decibold.** Until Tannay says otherwise, every
   post, Story and ad needs his "yes" first. (Mi Amor Paris autonomy does not carry over.)
2. **Every price in a post, caption, reply or ad must match decibold.com/products.json** at the
   time it goes out. Never state a discount you have not verified.
3. **Specs only from the listing** (watts, inputs, driver sizes, Bluetooth, HDMI ARC...). Several specs
   are still marked "confirm before launch" on the site: if a spec isn't in the live listing, leave it out.
   Never invent frequency response, battery, range, dB or "best in class" claims.
4. Never name competitors or other speaker brands. No comparisons: no "sound of the big names", no "half the price of...". Decibold is its own brand, not an alternative (Tannay, 20 Nov 2026).
5. Never invent reviews, ratings, customer numbers or order volumes.
6. Real product photos only: whole product, never cropped or AI-redrawn. No AI-generated people or
   rooms presented as real. Mark any AI imagery as AI (Metricool instagramData.isAiGenerated).
7. Links in captions are not clickable — point to "the link in our bio" / decibold.com.
8. Hashtags: max 5 per post.

## Brand
- Tagline: **"decibels made boldd"**: the doubled d is intentional, and it is ALWAYS all lowercase, including on end cards and logos, never "DECIBELS MADE BOLDD" (founder, 20 Nov 2026).
- Look: ink #100d0b, shell #ede4d6, bronze #a8763e. Fonts: Archivo (display), Newsreader (story).
- Products are white studio cutouts: on dark backgrounds place them on a shell-coloured plate
  (mix-blend-mode multiply equivalent) so they don't turn into white rectangles.
- Voice: confident, warm, about the feeling of sound in a room (movie nights, vinyl, the desk setup,
  the first bass hit). Short sentences. 1–2 emoji max. Avoid: "elevate", "immersive experience",
  "game-changer", "must-have", "stop scrolling", em dashes.

## Founder story (ethos) — full text in ops/BRAND_STORY.md
Use for trust lines: a speaker collector since childhood (brought one back from every trip), years as a DJ at
weddings/parties/events, ran a DJ Training Academy in Naraina Vihar, New Delhi (since closed), then the family
electronics business (acoustics, cabinets, amplification, tuning). Core idea: "specs tell you how loud a speaker
is, never how a song will make you feel." Don't add details beyond the story.

## Content direction
- **Positioning: MUSIC ONLY (Tannay, 18 Nov 2026).** Never pitch movies, TV, movie night or home theatre. Leave out HDMI ARC/TV angles; no #hometheatre.
- Only 8 listings, so variety comes from rooms, moments and setups, not new products.
- Best format: short real phone videos of the speakers playing (Tannay to shoot), plus static
  carousels 1080x1350 (setups, spec cards, "which setup fits your room").
- Stories 1080x1920: e.g. "Desk or living room?", "Bass or clarity?" (Reply 1 or 2), product of the day.
- Festive: wedding season (Nov–Feb), Christmas/New Year parties, house parties, gifting.

## Meta ads rules
- TBD — copy Mi Amor Paris's caps only after Tannay sets a Decibold daily cap and ad account.
- Adspirer usage is shared with Mi Amor Paris (15/15 used for Oct 2026).

## How a post is made
1. Pick the occasion/event and products (rotate; check ops/feed_used.md).
2. Live prices from decibold.com/products.json.
3. Photos: Google Drive (whitevenusbrands6@gmail.com), read with the Drive connector
   (search_files with parentId, then download_file_content). See "Drive photo library" below. Edit to fit the event (background, layout, text), keep the product whole.
4. Design 1080x1350 (feed) or 1080x1920 (Stories) in brand colours; open and check every image.
5. Commit + push to this repo, then schedule in Metricool (brand "Decibold") with the
   commit-pinned raw URL. Verify it shows as PENDING. Log it.

## Drive photo library (folder "Speakers" 1ESWNvCHyUINknEMt6gXecpFZOcEYJi6U)
Each product folder has subfolders: Ecommerce White Background, Creative, Model, Infographics, Video.
| Folder | ID |
|---|---|
| db201 (soundbar) | 1un8k9rIAxqFllgvO2k6P2xFRgs6nJ6Zp |
| db302 | 1lvEbFLHHhlkYdnWZ91yeKK_VFTvNQ1Gb |
| db403 | 1E4TiO-8KPu13an2Kd1rKaEWb3iDQPla8 |
| db 8 Inch Subwoofer | 1jEPUJb0zllnWAkjmF7twXdGDDvBavdTK |
| db 10 Inch Subwoofer | 1-EYxc-plSxPV8LF0oC7YIcWwQndQqhtC |
| db Stands | 1sZPYyv6l8O350fyzfmgDbk70e7Z66FjX |
| Group Images | 18mzsIRw-sUQm2bFtCUnUtBbD8E2j20gm |
| Boxes | 1UGpl77MLQ_46wTkEnSeHxjr2SeBF2wOX |
| Speaker Videos | 1X_2-6mM8QPBdDCA2TLHIenuo7TRO__6y |
Folder "decibold" (1h7BPOlErnbkCu0ifQsD2m69jTFvv0J9D) holds only a zip copy of "Speakers"; ignore it.
"Model" photos show real people from the shoot: fine to use, never edit faces/bodies.

## Log
Posts published → `ops/post_log.md`. Products/sets used in feed posts → `ops/feed_used.md`.
Ads changes → `ops/ads_log.md`.
