# Deployment note — VMG realtor referral page

**Status: built, in GitHub, NOT yet live on Netlify.** Paul approved deploy at `refer.vaughanmortgagegroup.ca` on Oct 26, 2026 ("Both — page live, then send"). Repo created and pushed Oct 26: https://github.com/vaughanmortgages-design/vmg-referral-page (public, branch `main`).

**Remaining step (one Netlify dashboard session, signed in as vaughanmortgages@gmail.com, team "Vaughan Mortgage Group"):** Add new site → Import an existing project → GitHub → `vmg-referral-page` → Deploy (netlify.toml already sets publish `.`, no build command). Then Site configuration → Domain management → add custom domain `refer.vaughanmortgagegroup.ca` (if Netlify asks for a DNS record at the registrar: CNAME `refer` → the site's `*.netlify.app` address). Then Forms → confirm `vmg-referral` detected → turn on email notifications to vaughanmortgages@gmail.com. Then run the phone test in this file.

## What's in the folder

| File | Purpose |
|---|---|
| `index.html` | The whole page — markup, CSS, and JS inline. No frameworks, no build step. |
| `assets/paul-bust.png` | Paul's photo (cutout from his own card art / campaign assets). |
| `assets/skyline.jpg` | Hero backdrop (Vaughan skyline, from the approved campaign set). |
| `assets/apple-touch-icon.png` (180) · `icon-192.png` · `icon-512.png` | Home-screen icons generated from Paul's bust on VMG navy. |
| `manifest.webmanifest` | Add-to-home-screen / standalone config ("Refer to Paul"). |
| `netlify.toml` | Publish the folder as-is (`publish = "."`), matching the ameliasworld.ca setup. |

## How to deploy (when Paul approves)

Same pattern as ameliasworld.ca — Paul's real Netlify account is **vaughanmortgages@gmail.com** (team "Vaughan Mortgage Group"); confirm the signed-in email before deploying.

1. **Netlify Drop:** drag this folder onto Netlify Drop, or connect a repo like the other one-pagers. No build command.
2. **After deploy, two dashboard steps:**
   - Forms → confirm `vmg-referral` is detected, and turn on **email notifications** to vaughanmortgages@gmail.com so a form referral lands in Paul's inbox (WhatsApp and email referrals reach him directly by design; the form is the only route that needs this).
   - Site name / domain per the URL choice below.
3. **Test all three routes** from a phone: WhatsApp opens with the prefilled message, email opens with subject "Client referral", form submits only with the consent box checked and shows the thank-you.

## URL — Paul's choice (not yet decided)

Suggested slug: **`refer`**. Options:

- A path on a domain he controls, e.g. `vaughanmortgagegroup.ca/refer` (if that site's hosting allows a static subfolder), or a page on the Netlify site, e.g. `<site>.netlify.app` with the page at root.
- A short subdomain, e.g. `refer.vaughanmortgagegroup.ca` pointed at the Netlify site — shortest to say out loud and to print on a card.

Recommendation: the subdomain — one word, easy to say across a desk, and the page *is* the whole site, so nothing else competes with the form. Final call is Paul's; do not point DNS until he picks.

## After it's live

- Add the URL to `~/workspace/vmg-referral-system/REFERRAL-PAGE.md` rollout steps and to the outreach drafts in that pack.
- Log every referral in `~/workspace/vmg-referral-system/referral-funnel.csv` (source = page-whatsapp / page-email / page-form / direct).
