# Thung Dong Farm Stay

The live site: six pages, built with Jekyll and served by GitHub Pages. No
external build step or dependencies to install — GitHub Pages builds Jekyll
automatically on every push to `main`. To preview locally, install Jekyll and
run `jekyll serve` from this folder.

```
index.html              Home
our-story.html          Ae, the farm's history, guest-built, returning guests
rooms-rates.html        Four rooms described and priced together
farm-life.html          A day unfolding, plus the full three-night itinerary
plan-your-visit.html    Logistics, seasons, what to bring, FAQ, enquiry
gallery.html            Photographs by theme, plus the two films
_layouts/default.html   Shared <head>, header and footer wrapper for every page
_includes/header.html   Nav bar (aria-current driven by each page's `nav:` front matter)
_includes/footer.html   Shared footer
_includes/schema-*.html Per-page JSON-LD, pulled in via each page's `schema:` front matter
assets/site.css         All styles
assets/site.js          Mobile nav toggle, and the footer's copyright year — the only script
```

Each page is just YAML front matter (`title`, `description`, `canonical`, and
`nav` for the current nav-highlight) followed by its unique body content. The
header, footer and `<head>` boilerplate live once each in `_includes/` and
`_layouts/`, instead of being duplicated across all six files.

## Placeholders

- **Images** — every dashed green box is an `.img-slot`. Replace the whole `<div>`
  with an `<img>`. The caption text inside says what the shot needs to be.
- **Logo** — `.logo-slot` in the header of each page. Swap the `<span>` for an `<img>`.
- **Editor notes** — the pink dashed blocks (`.note`). These are questions for Ae
  and build reminders. **Delete them all before launch**: `grep -rn 'class="note"'`.
- **Guest quotes** — square-bracketed in the markup. Pull the real wording from the
  old Guest Comments page.

## Still to confirm with Ae

1. Are the rates still current? The old site's were effective 1 January 2025.
2. A family taking the Sunset Room and the Bunk Room — two prices added, or a combined figure?
3. The jungle zip wire price.
4. Total sleeping capacity across the four rooms.
5. Burning season — what the farm is actually like in February to April.
6. Hot water, wifi and phone signal, mosquitoes, nearest clinic, safety around the animals.
7. Deposit and payment arrangement.
8. The animals' names, and what else is grown besides coffee and oranges.
9. The tricycle — it appears in a guest review and nowhere on the site.

## 301 redirects when the domain moves

The old URLs have years of accumulated links. Map every one of them:

| Old | New |
| --- | --- |
| `/our-philosophy.html` | `/our-story/` |
| `/about-the-farm.html` | `/our-story/` |
| `/guest-comments.html` | `/our-story/` |
| `/staying-with-us.html` | `/rooms-rates/` |
| `/farm-stay-accommodation.html` | `/rooms-rates/` |
| `/daily-fare.html` | `/rooms-rates/` |
| `/activities.html` | `/farm-life/` |
| `/animals--crops.html` | `/farm-life/` |
| `/thai-country-food.html` | `/farm-life/` |
| `/a-sample-itenerary.html` | `/farm-life/` |
| `/tours--transfers.html` | `/plan-your-visit/` |
| `/climate.html` | `/plan-your-visit/` |
| `/contact-us.html` | `/plan-your-visit/` |
| `/gallery.html` | `/gallery/` |
| `/blog.html` and `/blog/*` | `/farm-diary/` (one-to-one for each post) |

## Fixes carried over from the old site

- `Chaing Mai` misspelled in the homepage meta description — corrected.
- `itenerary` misspelled in a page title and URL — gone.
- `Kathrong` → `krathong` throughout.
- `meta keywords` removed. Search engines stopped using it around 2009.
- Table-based layout replaced. Every page now has a unique title and description.

## Structured data

- Home — `LodgingBusiness` (latitude and longitude still need filling in).
- Our story — `Person` for Chaiwat "Ae" Pankaew, linked to the business.
- Farm life and Plan your visit — `FAQPage`.

Keep the name, address and email identical here, on the Google Business Profile,
and on Instagram and Facebook. That consistency is what lets an AI assistant
answer questions about the farm with confidence.
