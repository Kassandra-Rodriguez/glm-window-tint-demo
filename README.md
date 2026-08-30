# GLM Window Tinting — concept site

A one-page pitch site for **GLM Window Tinting**, 4300 N Mesa St, El Paso, TX.
Static: `index.html` + `styles.css` + `script.js` + `assets/`. No build step.

Built from the `local-business-search/` demo template (`j-elite-demo` skeleton),
reskinned to GLM's storefront colours. Bilingual EN/ES via `data-en` / `data-es`.

The hook: **14 years on N Mesa, a 3M-authorized dealer, ~70 reviews — and no
website.** Their Meta ads dead-end in Facebook Messenger with no quote form. This
site gives ad clicks and Google searches somewhere to land: a vehicle-specific
"get a tint quote" form, an interactive tint-level preview, hours and a map.

Hero leads with the customer benefit for El Paso — heat and sun — not with the
shop's résumé: **"Beat the El Paso sun. Keep the view."** + one line of what/how,
three benefit bullets. The trust bar was rewritten from plain credentials to
reasons-to-buy (heat rejection, 99% UV / interior protection, lifetime warranty,
social proof), each still anchored to a verifiable fact.

---

## Verified vs. placeholder

| Item | Status | Source / note |
|---|---|---|
| Name "GLM Window Tinting" | **Verified** | Storefront + pylon signage in client photos (listing calls it "GLM Window Tint") |
| 4300 N Mesa St, El Paso, TX 79902 | **Verified** | Prospect sheet; BBB profile; visible plaza (Mesa Smoke Shop / Franco Auto Electric) |
| Phone (915) 727-7342 | **Verified** | Prospect sheet / BBB |
| 3M-authorized dealer | **Verified** | "3M CERAMIC TINT AVAILABLE" storefront banner; listing ("3M dealer") |
| In business since 2012 (~14 yrs) | **Verified** | Prospect sheet ("14 years in business", "est. 2012") — copy says "since 2012" |
| Automotive + residential + commercial | **Verified** | Listing; client photos show car, home picture-window and flat-glass work |
| Windshield / sun-strip tint | **Verified** | "WINDSHIELD TINT WITH CLEAR…" sub-sign in storefront photo |
| Walk-ins welcome / open Saturdays | **Verified** | Prospect sheet ("open Saturdays / 'come visit us'") |
| "Blocks 99% of UV" (hero, trust bar) | **Industry-standard — confirm** | ~99% UV rejection is a near-universal property of quality window film and is what 3M markets; still verify against the spec sheet for the film lines GLM actually installs before publishing. |
| "Rejects the heat / less A/C", "cooler cabin" | **Directional — confirm** | True of carbon and especially 3M ceramic film; no specific % (e.g. IR or TSER) is claimed on the page. Add a number only if it's from GLM's film spec. |
| 4.5 rating, ~70 reviews | **Verified, source-specific** | Yelp 4.5 / ~70 per prospect sheet. Trust bar says "4.5 on Yelp". Re-check the live number before launch; add Google rating if one exists. |
| IG @glm_windowtint · FB /GlmWindowTint | **Verified** | Prospect sheet |
| Exact business hours | **PLACEHOLDER** | Footer + Visit section say "confirm current hours". Get real hours. |
| Prices ("$XX", "$XXX", "from") | **PLACEHOLDER** | Packages section is `$XX` / `$XXX` literal placeholders + a disclaimer paragraph. Replace with GLM's real starting prices or delete the figures and keep "Get a quote". |
| Lifetime warranty wording | **PLAUSIBLE — confirm** | 3M dealer film typically carries a lifetime warranty; confirm GLM's exact terms before publishing. |
| "2 to 3 hours" install time | **PLACEHOLDER** | Typical full-car figure in the "How it goes" step; confirm. |
| Texas VLT / street-legal note (shade section) | **General, confirm** | "Texas limits how dark front side windows can be" is true directionally; the page tells the customer to confirm current law. Do not add a specific % without checking. |
| Logo | **Redrawn, not their file** | Inline SVG in header and footer: a filled sleek sports-car side silhouette (two wheel-arch cutouts) in signage green, next to "GLM" in green with "WINDOW TINTING" stacked below in white. It echoes the real storefront logo (green GLM wordmark, WINDOW TINTING beneath, car silhouette above). Replace with GLM's actual vector when they provide one. |
| Form submit | **DEMO ONLY** | `script.js` shows a success panel; nothing is sent. Wire to text/email/CRM before launch (see comment in `script.js`). |
| `robots` noindex | Intentional | `<meta name="robots" content="noindex, nofollow">` while it's a concept. |

---

## Photos

Client-supplied shots live in `assets/` under their original names
(`car-tint*.jpg`, `truck-tint.jpg`, `window-tint.jpg`). Optimized copies:

| File | From | Used for |
|---|---|---|
| `hero.jpg` | `truck-tint.jpg` (cropped to the sign band) | Hero background: GLM storefront channel-letter sign |
| `g0-m2-front.jpg` | `car-tint5.jpg` | Gallery: BMW M2, front |
| `g1-m2-rear.jpg` | `car-tint3.jpg` | Gallery: BMW M2, rear, dark tint |
| `g2-bmw-door.jpg` | `car-tint4.jpg` | Gallery: BMW 2-Series, front-window tint |
| `g3-windshield.jpg` | `car-tint2.jpg` | Gallery: Lexus, 70% windshield view |
| `g4-tesla-shop.jpg` | `car-tint.jpg` | Gallery: Tesla, install in progress |
| `g5-residential.jpg` | `window-tint.jpg` | Gallery: home picture window |

The **tint-level preview** ("See the shade before we cut it") is a pure inline
SVG: a stylised window with a desert/mountain scene behind it and a `<rect>`
tint layer whose `opacity` animates between the 70 / 50 / 35 / 20 / 5 % buttons.
No photo, so it can't be wrong about a real vehicle.

## Locations section: embedded Google map

The "Visit us" block pairs a facts column (address, phone, hours, area list,
"Get directions") with an **embedded Google map** in the right grid slot.

- `<iframe class>` inside `.visit-map`, `src` =
  `https://maps.google.com/maps?q=<address>&t=&z=15&ie=UTF8&iwloc=&output=embed`.
  This is the keyless Google Maps embed: no API key, no billing. The final 200
  response carries no `X-Frame-Options` and no framing CSP, so it renders on any
  origin.
- `loading="lazy"`, `referrerpolicy="no-referrer-when-downgrade"`, a `title` for
  a11y, and a non-interactive `.visit-map-tag` pill showing the street address.
- Styled with `aspect-ratio:5/4` (1/1 on mobile), `border-radius`, and a light
  `filter: grayscale(.15) contrast(1.03)` so it sits in the dark theme without
  looking pasted on. The map itself stays fully legible and interactive.
- To move it, change the `q=` address string. To swap for the official
  "Share > Embed a map" code, replace the whole `src` with Google's `pb=` URL.

This map pattern is now the default for any demo whose business has a real
street address (replaces the photo-plus-pin treatment).

---

## Palette (`styles.css` `:root`)

```css
--ink:#0B0F0C;         /* near-black ground */
--jet:#12160F;         /* alt sections / cards */
--jet-2:#191E15;       /* inputs / raised surfaces */
--line:#2A3122;        /* hairlines */
--green:#7BC142;       /* signage lime — buttons, links, accents  ← estimated */
--green-bright:#A8E271; /* gradient top / highlights */
--green-deep:#4C871F;  /* pressed / deep borders */
--white:#F3F5EF;
```

**The green is eyeballed from the storefront photos, not sampled.** Before launch,
open a sharp photo of the sign (or their logo file) and sample the real lime;
replace `--green` / `--green-bright` / `--green-deep`. Everything else derives
from these three.

Fonts: Oswald (headings/UI) + Inter (body), from Google Fonts.

---

## Run locally

```
cd GLM-Window-Tint
python3 -m http.server 8000
# open http://localhost:8000
```

## Ship (GitHub Pages)

```
cd GLM-Window-Tint
git init -q && git add -A
git -c user.name="Kassandra-Rodriguez" -c user.email="kassandra.rodriguez2014@gmail.com" \
  commit -q -m "GLM Window Tinting concept site"
git branch -M main
gh repo create glm-window-tint-demo --private --source=. --remote=origin --push
```

Then (assistant is blocked from these):

```
gh repo edit Kassandra-Rodriguez/glm-window-tint-demo --visibility public --accept-visibility-change-consequences
gh api --method POST /repos/Kassandra-Rodriguez/glm-window-tint-demo/pages -f "source[branch]=main" -f "source[path]=/"
```

Live ~1 min later at `https://kassandra-rodriguez.github.io/glm-window-tint-demo/`.

---

## Outreach talk track

Lead with the compliment + the gap — not a critique:

> "You've been on N Mesa 14 years, you're a 3M dealer, you've got around 70
> reviews — but when someone Googles GLM or taps your Facebook ad, there's no
> website for them to land on. It dead-ends in Messenger with no way to get a
> price. I built you a one-pager: they pick what needs tint, drop in their year/
> make/model, and it texts you the lead — plus your hours, a map, the 3M badge,
> and a little slider so they can see 35% vs 5% before they even call. Here's the
> link — tell me what's wrong and I'll fix it."

$300 one-pager. Everything on the page that isn't verified (hours, prices,
warranty terms) is flagged on-page as "confirm" so GLM fills the blanks.
