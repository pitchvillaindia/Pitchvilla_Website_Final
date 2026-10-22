# Pitchvilla website: developer handoff

This folder holds the final design files for **two things**:

1. **The main Pitchvilla website** at `pitchvilla.com`
2. **The Educore single-page site** at `pitchvilla.com/educore`

Everything else in the design project (decks, brochures, old versions) has been left out on purpose.

## 1. Main website (`pitchvilla.com`)

| File | URL |
|---|---|
| `Pitchvilla Website v4.dc.html` | `/` (home page) |
| `About.dc.html` | `/about` |
| `Apply.dc.html` | `/apply` (accepts `?type=apply`) |
| `Contact.dc.html` | `/contact` |
| `Entrepreneurship Programs.dc.html` | `/programs` |
| `Interview Prep.dc.html` | `/interview-guide` |
| `Pitchvilla Consulting Group.dc.html` | `/services` |
| `Launch Your Startup.dc.html` | `/services/launch-your-startup` |
| `Idea Validation.dc.html` | `/services/idea-validation` |
| `Business Strategy.dc.html` | `/services/business-strategy` |
| `Digital Marketing.dc.html` | `/services/digital-marketing` |
| `Hiring and Team Building.dc.html` | `/services/hiring-and-team-building` |
| `Financial Analysis.dc.html` | `/services/financial-analysis` |
| `Investor Readiness.dc.html` | `/services/investor-readiness` |
| `Pitch Deck Creation.dc.html` | `/services/pitch-deck-creation` |
| `Pitch to Investors.dc.html` | `/services/pitch-to-investors` |
| `Privacy Policy.dc.html` | `/privacy-policy` |
| `Terms and Conditions.dc.html` | `/terms` |

The URL slugs above are suggestions, so change them if needed. The pages link to each other by file name (e.g. `href="About.dc.html"`), so **rewrite every internal link to the final URL** when you build.

All pages share the same header (logo · Home · About us ▾ · 100X Forge · Programs ▾ · Services ▾ · Contact us · yellow "Apply to 100X Forge" button) and the same footer. Build them once as shared components.

## 2. Educore single pager (`pitchvilla.com/educore`)

| File | URL |
|---|---|
| `Educore.dc.html` | `/educore` |

- This is **one page**, served as a **sub-path of the main domain**, not a separate domain or subdomain.
- It has its **own header** ("AERO EDUTECH · Powered by Pitchvilla") with a three-link nav that scrolls within the page, plus its own enquiry form and footer. **Do not** add the main Pitchvilla header or footer to it.
- It uses the same fonts, colours and spacing as the main site.
- The main website does not link to it in the nav. Add a link only if Pitchvilla asks for one.

## Design system (both sites)

- **Font:** Poppins (Google Fonts), weights 300–700.
- **Colours:** `#FBF8F1` page · `#F3EDE0` alt sections · `#E9E1CF` image backgrounds · `#FFCC00` accent / buttons · `#1C1410` text · `#4A3F37` / `#6B5E54` muted text. No other colours.
- **Content width:** `max-width:1280px`, side padding `clamp(24px,6vw,96px)`. The **home page hero and its header are wider** (`max-width:1600px`, side padding `clamp(24px,4vw,64px)`) so the video can be larger. Keep that difference.
- **Section spacing:** 88px top/bottom on desktop, 48px on mobile. Heading-to-content gap is `clamp(32px,3.5vw,48px)`.
- All styles are written inline on each element, so read values straight from the markup.

## Things to build or connect

1. **Forms: not connected yet.** Booking (home page workshops pop-up), Apply, Contact and the Educore enquiry form currently save only to the visitor's browser. Connect each one to email or a form/CRM service before launch.
2. **Home hero video:** `assets/hero-video.mp4` (16:9). It plays automatically, muted and on loop, with a Pause/Play button. It shows paused for users with "reduce motion" turned on. Compress it for the web and add a poster image.
3. **Animations:** scroll reveals (fade/rise, count-up stats, word-by-word text, staggered items, accordions) are driven by JS in each page's logic block. Recreate them with your animation approach and check element position on scroll, not class toggles only.
4. **Responsive:** each page includes `@media` rules in its `<style>` block (tablet ≤1100px, mobile ≤900px / ≤600px). Match them.

## Running the files locally

Each `.dc.html` opens directly in a browser as long as `support.js`, `image-slot.js`, `autoscroll.js`, `motion.js` and the `assets/` folder sit beside it. They are **design references**. Rebuild them in your production stack rather than shipping these files as they are.
