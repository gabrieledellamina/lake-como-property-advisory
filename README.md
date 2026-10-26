# Lake Como Property Advisory — Astro website

A multi-page, English-language boutique consultancy website built with Astro. Designed for free static deployment on Cloudflare Pages.

## Included pages

- `/` — Home, parallax-style Lake hero, service overview, lifestyle preview, journal preview and enquiry form.
- `/services/` — overview of all services.
- `/services/tax-advisory/` — tax & relocation coordination, with careful scope disclaimer.
- `/services/project-management/` — design coordination, cost estimates, permit-process coordination and project controls.
- `/services/construction-management/` — technical/economic site management and quality monitoring.
- `/services/due-diligence/` — real estate due diligence and IVS-informed valuation support.
- `/lifestyle/` — villas, water sports, nature, Milan and St. Moritz connections.
- `/journal/` — articles overview.
- `/journal/italy-flat-tax-300000-euro/` — first article on Italy's €300,000 new-resident lump-sum tax.
- `/thank-you/` — form success page.

## Before going live — important edits

1. **Confirm the full domain.** `astro.config.mjs` currently uses `https://lakecomopropertyadvisory.com`. If your purchased domain has another extension, update the `site` value and the form's `_next` URL.
2. **Configure the contact form.** Open `src/components/ContactForm.astro` and replace `YOUR_EMAIL@example.com` in the `action` attribute with the real address that should receive enquiries. Replace the `_next` URL if the domain differs. FormSubmit is a third-party form relay; on first use, it may send an activation email to the recipient address. Test the form after activation. It is not a built-in Cloudflare service.
3. **Add a real privacy notice.** The checkbox is included, but before publishing you should add a privacy page/notice that identifies the data controller, purpose, legal basis, retention period, recipients and user rights. Get appropriate advice for your circumstances and applicable privacy law.
4. **Review business claims.** Confirm that all descriptions match the services you are entitled and equipped to provide. Statutory design, certifications, formal valuations, tax advice and legal opinions must be handled by appropriately qualified/authorised professionals where required.
5. **Images.** The initial version uses remote images from Unsplash's image CDN. Before launch, check the current licence/terms for each image, replace any image that does not fit the brand, and consider downloading properly licensed optimised images into `public/images/` for long-term reliability and performance.
6. **Tax article.** The article is general information, not tax advice. Re-check legislation and official guidance before publishing or updating it.

## Run locally (optional)

Install Node.js LTS from https://nodejs.org/ and then run in this folder:

```bash
npm install
npm run dev
```

To create the static production build:

```bash
npm run build
```

Astro outputs the website to `dist/`.

## Publish free on Cloudflare Pages

1. Create a public GitHub repository called `lake-como-property-advisory` at https://github.com/new.
2. Upload the contents of this project folder (not the ZIP file itself). `package.json`, `astro.config.mjs` and `src/` should sit at the repository root.
3. In https://dash.cloudflare.com/, open **Workers & Pages** and create a Pages project connected to Git.
4. Choose the GitHub repository and configure:
   - Framework preset: **Astro**
   - Build command: `npm run build`
   - Build output directory: `dist`
   - Root directory: leave blank
5. Deploy and test the `*.pages.dev` address.
6. In the Cloudflare Pages project, open **Custom domains** and add your full purchased domain. Follow the DNS instructions displayed by Cloudflare. Do not change nameservers or delete DNS records blindly, especially if the domain is already used for email.
7. Test every page, mobile navigation, links and the contact form before sharing the site publicly.

## Costs

Astro is open source and Cloudflare Pages has a free plan suitable for many static websites. Domain renewal, email hosting, optional third-party services, and any professional/legal compliance work may still cost money. Free-tier limits and service terms can change; check Cloudflare's current plan documentation.


### Image update
The repeated lakeside-pier image has been replaced with a photograph of Villa del Balbianello on Lake Como, available under the Unsplash License: https://unsplash.com/photos/a-view-of-a-courtyard-through-an-archway-K7HkxnJbWok. Images are still loaded from Unsplash, so the visitor needs an internet connection to view them.
