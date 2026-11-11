# Villa Mare: SEO and local-search implementation

This document contains paste-ready copy and markup for the existing Slovenian and English pages, plus a Google Business Profile eligibility checklist.

## Use the right live URLs

The repository currently publishes at the GitHub Pages project URL shown in `sitemap.xml`:

- Slovenian: `https://gorazdvrabic-sudo.github.io/username.github.io/`
- English: `https://gorazdvrabic-sudo.github.io/username.github.io/index_en.html`
- German: `https://gorazdvrabic-sudo.github.io/username.github.io/index_de.html`
- Italian: `https://gorazdvrabic-sudo.github.io/username.github.io/index_it.html`

Use these URLs consistently for canonicals, language alternates, sitemap entries, and social metadata until a custom domain is configured. If a custom domain is adopted, update all of them together. The address currently available to the site is the locality Karigador and the map coordinates below; do not publish an unverified street address or postal code.

## Slovenian page copy

**Title**

> Villa Mare – apartmaja Olive in Lavender v Karigadorju, Istra

**Meta description**

> Odkrijte apartmaja Olive in Lavender v Karigadorju v Istri, približno 200 m od plaže. Preverite opremo, parkiranje in fotografije ter nam pošljite povpraševanje.

**H1**

> Apartmaja ob morju v Karigadorju – Villa Mare

**Opening paragraph**

> Villa Mare ponuja apartma Olive za 2–3 osebe in apartma Lavender za največ 4 osebe v Karigadorju v Istri. Apartmaja sta približno 200 metrov od plaže. V opisu nastanitve preverite opremo, možnosti parkiranja in fotografije, za razpoložljivost pa nam pošljite povpraševanje.

**Local section heading and paragraph**

> ### Oddih v Karigadorju, Istra
>
> Karigador je obmorsko naselje v Istri na Hrvaškem. Villa Mare je približno 200 metrov od plaže; v okolici lahko raziskujete obalo in bližnje istrske kraje. Za pot do nastanitve uporabite zemljevid ali nas pred prihodom kontaktirajte za navodila.

## English page copy

**Title**

> Villa Mare – Olive & Lavender Apartments in Karigador, Istria

**Meta description**

> Discover Villa Mare’s Olive and Lavender apartments in Karigador, Istria, about 200 m from the beach. Check amenities, parking and photos, then contact us to ask about availability.

**H1**

> Seaside apartments in Karigador, Istria – Villa Mare

**Opening paragraph**

> Villa Mare offers the Olive apartment for 2–3 guests and the Lavender apartment for up to 4 guests in Karigador, Istria. Both apartments are approximately 200 metres from the beach. Explore the amenities, parking information and photos, then contact us to ask about availability.

**Local section heading and paragraph**

> ### Stay in Karigador, Istria
>
> Karigador is a coastal village in Istria, Croatia. Villa Mare is approximately 200 metres from the beach, with the Istrian coast and nearby towns to explore. Use the map for directions or contact us before arrival for local guidance.

Use “approximately/about 200 m” consistently unless the distance has been measured and verified. Keep all amenities and availability statements accurate; useful original information is preferable to repeating search phrases.

## Head markup for each page

Replace the existing title and description on each localized HTML page with its corresponding copy above. Add the page-specific canonical, language alternates, and Open Graph tags. These URLs match the current project deployment; replace them if the live site moves to a custom domain.

For `index.html`:

```html
<title>Villa Mare – apartmaja Olive in Lavender v Karigadorju, Istra</title>
<meta name="description" content="Odkrijte apartmaja Olive in Lavender v Karigadorju v Istri, približno 200 m od plaže. Preverite opremo, parkiranje in fotografije ter nam pošljite povpraševanje." />
<link rel="canonical" href="https://gorazdvrabic-sudo.github.io/username.github.io/" />
<link rel="alternate" hreflang="sl" href="https://gorazdvrabic-sudo.github.io/username.github.io/" />
<link rel="alternate" hreflang="en" href="https://gorazdvrabic-sudo.github.io/username.github.io/index_en.html" />
<link rel="alternate" hreflang="de" href="https://gorazdvrabic-sudo.github.io/username.github.io/index_de.html" />
<link rel="alternate" hreflang="it" href="https://gorazdvrabic-sudo.github.io/username.github.io/index_it.html" />
<link rel="alternate" hreflang="x-default" href="https://gorazdvrabic-sudo.github.io/username.github.io/" />
<meta property="og:type" content="website" />
<meta property="og:locale" content="sl_SI" />
<meta property="og:title" content="Villa Mare – apartmaja Olive in Lavender v Karigadorju, Istra" />
<meta property="og:description" content="Apartmaja v Karigadorju v Istri, približno 200 m od plaže. Oglejte si opremo in fotografije ter pošljite povpraševanje." />
<meta property="og:url" content="https://gorazdvrabic-sudo.github.io/username.github.io/" />
<meta property="og:image" content="https://gorazdvrabic-sudo.github.io/username.github.io/images/hero.png" />
```

For `index_en.html`, use the English title and description above, canonical URL `https://gorazdvrabic-sudo.github.io/username.github.io/index_en.html`, `og:locale` of `en_GB`, and that English URL for `og:url`. Include the same five `alternate` links on **every** language page, including German and Italian. Each alternate must point to a real, indexable page, and the set should be reciprocal.

## Local accommodation structured data

This JSON-LD uses only current site facts: name, locality, country, coordinates, phone, email, site URL and map link. Put it in the `<head>` of each language version and keep the values in sync. Do not treat markup as a way to make an ineligible rental qualify for a Business Profile or to promise a Google rich result.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "LodgingBusiness",
  "name": "Villa Mare",
  "url": "https://gorazdvrabic-sudo.github.io/username.github.io/",
  "email": "villamare.olive.lavender@gmail.com",
  "telephone": "+38641776608",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Karigador",
    "addressRegion": "Istria",
    "addressCountry": "HR"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 45.3595613983202,
    "longitude": 13.56048904460079
  },
  "hasMap": "https://www.google.com/maps?q=45.3595613983202,13.56048904460079",
  "containsPlace": [
    {
      "@type": "Apartment",
      "name": "Apartma Olive",
      "occupancy": {
        "@type": "QuantitativeValue",
        "minValue": 2,
        "maxValue": 3
      }
    },
    {
      "@type": "Apartment",
      "name": "Apartma Lavender",
      "occupancy": {
        "@type": "QuantitativeValue",
        "maxValue": 4
      }
    }
  ]
}
</script>
```

Review the schema values against the actual property before publishing. If the exact address is known and publicly shareable, add the verified street address and postal code; otherwise, do not guess. Validate the rendered pages with Google’s Rich Results Test and Schema.org Validator.

## Google Business Profile compliance checklist

Google’s current eligibility guidance excludes rental or for-sale properties such as vacation homes and vacant apartments from individual Business Profiles. Therefore, do **not** create separate profiles for Villa Mare’s Olive and Lavender apartments merely to target Maps results. A separate profile is appropriate only for a genuinely eligible business (for example, a property-management office) that independently satisfies Google’s current requirements for in-person customer contact at the listed location. Check the latest [Google Business Profile eligibility and ownership guidelines](https://support.google.com/business/answer/13763036?hl=en) before creating or claiming a profile.

If the owner or manager operates a separately eligible, customer-facing business, use this checklist:

- [ ] Confirm the actual business—not just the rental property—is eligible under Google’s guidelines.
- [ ] Use the real-world business name as used on signage and customer-facing materials; do not add location or service keywords to the name.
- [ ] Choose the most accurate available primary category; add only genuinely applicable additional categories.
- [ ] Enter a precise address only if customers are served there in person and the address meets Google’s requirements. Hide an address for a service-area business when the guidelines require it.
- [ ] Keep name, address, phone, website, and hours accurate and consistent on the website and other authoritative listings.
- [ ] Set accurate regular and special hours. For a seasonal operation, represent the operating period truthfully.
- [ ] Add a concise, factual description and real photos of the eligible business and its services. Do not use the description as a keyword list.
- [ ] Use the official website URL and appropriate booking/contact links; test them on mobile.
- [ ] Ask real guests or customers for honest reviews without offering incentives, filtering who is asked, or scripting review wording; respond professionally.
- [ ] Keep ownership and access secure, and periodically review profile details for accuracy and policy changes.
- [ ] Do not create duplicate profiles for the same business, use a virtual office as a storefront, or claim a rental unit that does not qualify.

For the vacation rental itself, concentrate on clear website content, accurate accommodation information, original photos, consistent contact details, eligible booking channels, and useful local guidance. Google Maps inclusion or a higher ranking is not guaranteed by structured data or profile activity.

## Technical SEO follow-up

- Keep `robots.txt` pointing at the production sitemap, and submit the sitemap in Google Search Console after confirming the deployed URLs.
- Keep one canonical URL per language page. Avoid canonicals that all point to Slovenian; language pages are distinct useful content.
- Put reciprocal `hreflang` links in each page’s `<head>` as well as consistent alternates in the sitemap.
- Use descriptive, truthful alt text and filenames for actual property photos. Check that the existing case-sensitive image paths resolve on GitHub Pages.
- Optimize photo file sizes and dimensions; reserve eager/high-priority loading for the actual above-the-fold hero asset and lazy-load below-the-fold images.
- Add or update a custom domain only when it is configured in GitHub Pages, then change canonical, `hreflang`, sitemap, robots, and social URLs together.
- Measure queries and page performance in Search Console and use guest questions to add genuinely helpful content. Do not promise specific rankings.
