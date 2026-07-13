# Mission 104 — Website Owner's Guide

This folder IS your entire website. No database, no admin panel, nothing to
update or patch. Edit a file, and the live site updates itself about a
minute later (once connected to Cloudflare Pages).

## The files

| File | What it is |
|---|---|
| `index.html` | Homepage |
| `services.html` | Services page |
| `how-it-works.html` | Process & pricing page |
| `faq.html` | The honest Q&A (EDIT THIS — make it sound like you) |
| `contact.html` | Contact page (HubSpot form goes here) |
| `css/style.css` | The look: colors, fonts, spacing. Rarely needs touching. |
| `images/` | Put your real photos here |

## Placeholders you must replace before launch

Search each file (Ctrl+F / Cmd+F) for the word `PLACEHOLDER`:

1. `PLACEHOLDER-YOUR-EMAIL` — your business email (appears in footer of
   every page, contact page, and once in index.html near the top)
2. `PLACEHOLDER-YOUR-PHONE` — your business phone (the red "Emergency?"
   button in the top navigation of every page, footer of every page, and
   the contact page)
3. `PLACEHOLDER-YOUR-DOMAIN` — your domain (once, near the top of index.html)
4. The HubSpot form slot in `contact.html` — see "Wire the form" below
5. Read the FAQ answers in `faq.html` one more time — they are written in your voice; adjust any wording that does not sound like you
6. If you change the business name from "Mission 104": search-and-replace
   "Mission 104" across all five HTML files.

## How to edit text

Every word on the site lives in the five HTML files. To change a sentence:
1. Open the file on GitHub → click the pencil icon (Edit)
2. Find the text (Ctrl+F), change it
3. Click "Commit changes" — that's it. Live in ~1 minute.

Don't worry about breaking things: GitHub keeps every version forever.
Any change can be undone.

## How to add your real photos

1. Upload the photo to the `images/` folder on GitHub
   (Add file → Upload files)
2. In the HTML, find the placeholder block:
   `<div class="photo-slot"><span>[ Your photo — the closet before ]</span></div>`
3. Replace that whole block with:
   `<img src="images/your-photo-name.jpg" alt="Messy IT closet before cleanup">`
   (Write a short honest description in the alt text — it helps SEO and
   accessibility.)

## Wire the form (HubSpot)

1. In HubSpot: Marketing → Forms → Create form → choose "Embedded form"
2. Add fields: Name, Company, Email, Phone, a dropdown called
   "What do you need help with?" (options: IT closet cleanup / Cabling /
   Network issues / Desktop or printer help / Something else),
   and a message box.
3. Publish the form and copy the EMBED CODE it gives you.
4. In `contact.html`, find the big comment that says
   "PASTE YOUR HUBSPOT FORM EMBED CODE HERE", delete the
   `<div class="form-slot"> ... </div>` block below it, and paste the
   embed code in its place.

Every submission now creates a lead in your CRM automatically, sorted by
the dropdown answer, and emails you a notification.

## Publish (one-time setup)

1. Create the site on GitHub: New repository → name it (e.g. `mission104-site`)
   → upload ALL files in this folder (keep the folder structure).
2. Cloudflare Pages: Workers & Pages → Create → Pages →
   Connect to Git → pick your repository → Framework preset: None →
   Build command: (leave empty) → Build output directory: `/` → Deploy.
3. Your site is live on a temporary `*.pages.dev` address immediately.
4. Custom domain: in the Pages project → Custom domains → add your domain
   and follow the DNS prompt (one click if your DNS is on Cloudflare).
5. Analytics: Cloudflare dashboard → Web Analytics → enable for your site.

## Changing the look (optional)

Colors and fonts are defined at the very top of `css/style.css` in the
`:root` block, with comments. Change a hex code there and it changes
everywhere.
