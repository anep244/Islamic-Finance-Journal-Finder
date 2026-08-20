# The Index — Islamic Finance & Economics Research Catalogue

A static, web-based research tool built for INCEIF's researchers, academics, and students to discover relevant articles across Islamic finance, banking, economics, and management journals through keyword-based searching.

The platform combines bibliographic records from 14 journals into a single searchable catalogue — by article title, abstract, author, or journal name — with live catalogue statistics and journal-level browsing.

## Features

- **Keyword-based article discovery** — search across title, abstract, authors, and journal name at once
- **Journal filtering** — browse by individual journal via quick-select chips (top 3 shown, with an "Expand" option to reveal the rest)
- **Sortable results** — newest first, oldest first, most cited, or title A–Z
- **Live catalogue statistics** — total articles, journals covered, and years spanned, animated on load
- **Expandable abstracts** — click any result to reveal its full abstract snippet and a link to the source
- **World clock strip** — live time across major Islamic finance hubs (Kuala Lumpur, Dubai, Jakarta, London, New York, Riyadh)
- **Visit counter** — running count of page visits
- Fully static — no server, database, or backend required

## Coverage

Currently indexes **4,293 articles** across **14 journals**, spanning **1987–2026**, including:

- Journal of Islamic Marketing
- Borsa Istanbul Review
- Journal of Islamic Monetary Economics and Finance
- International Journal of Economics, Management and Accounting
- Journal of Muamalat and Islamic Finance Research
- Journal of Emerging Economies and Islamic Research
- Journal of Islamic Accounting and Business Research
- Journal of King Abdulaziz University Islamic Economics
- Journal of Islamic Finance
- ISRA International Journal of Islamic Finance
- International Journal of Islamic Economics and Finance Research
- Qudus International Journal of Islamic Studies
- International Journal of Islamic Business
- International Journal of Islamic Finance and Sustainable Development

This is an expanding database — more journals can be merged in as new exports become available.

## Files

- `index.html` — the site itself (structure, styling, and search logic)
- `articles.json` — the combined article dataset the page reads from
- `combined_articles.csv` — the same combined dataset in spreadsheet form, with full original bibliographic fields (citations, DOI, ISSN, volume/issue, page numbers, etc.) for offline analysis or re-import
- `robots.txt` — tells search engines they may crawl the site
- `sitemap.xml` — lists the homepage plus one deep link per journal, for search engines to discover

Both `index.html` and `articles.json` must stay in the same folder — the page fetches the JSON at load time. All five files should be deployed together.

## Live site

Hosted at: **https://anep244.github.io/the-index/**

## Search engine visibility

The site is set up to be indexable by Google and other search engines:

- `<meta name="description">`, canonical URL, and Open Graph/Twitter tags are set in `index.html`'s `<head>`, using the live URL above.
- Deep links (`?q=keyword` and `?journal=Journal+Name`) pre-fill the search box and show results automatically on load — this is what lets a search engine (or a shared link) land directly on a filtered result set, since the results normally only appear after clicking Search.
- `robots.txt` and `sitemap.xml` are included at the site root and must be deployed alongside `index.html`.
- After deploying, submit the site in [Google Search Console](https://search.google.com/search-console): verify the domain, submit `sitemap.xml`, and use "Request Indexing" on the homepage to speed up the first crawl.

## Updating the catalogue

- **A few edits or additions:** open `articles.json` and add or edit entries directly (fields: `t` title, `a` authors, `y` year, `j` journal, `ab` abstract, `u` source URL, `c` citation count).
- **A new journal's worth of records:** merge a new CSV export (same format as the source files) into `combined_articles.csv` and regenerate `articles.json` from it.

## Status

Work in progress. Planned additions include further journal coverage and ranking metadata (Scopus Quartile, Web of Science, ABDC, MyCite) alongside the article-level search.
