# Global Escape Research Ledger

## Purpose

This folder maintains a job-first relocation route for a founder-side AI systems, product, and operations builder. The route tests a country through useful work before a foreign Master’s commitment.

Canonical presentation: [`../GLOBAL_ESCAPE_ROADMAP.html`](../GLOBAL_ESCAPE_ROADMAP.html)

Central data layer: [`opportunity_map_data.json`](opportunity_map_data.json)

Parallel company research packet: [`delegated_company_research.json`](delegated_company_research.json)

Primary checks for the delegated packet: [`delegated_primary_checks.json`](delegated_primary_checks.json)

Editable strategy diagram: [`../GLOBAL_ESCAPE_ENTRY_STRATEGY.excalidraw`](../GLOBAL_ESCAPE_ENTRY_STRATEGY.excalidraw)

## Current Curation

- **Japan:** 10 ranked targets.
- **Singapore:** 10 ranked targets.
- **Contacts:** 3 per company, 60 total.
- **Apollo gate:** 60/60 contacts have Apollo `email_status=verified`, a LinkedIn URL, and a current-employer match.
- **Official evidence pages:** 58/60 returned direct 2xx/3xx responses. The remaining two are Carro pages protected by a 403 web-application firewall response; the links are retained and labelled access-limited.
- **LinkedIn recheck:** 60/60 canonical URLs were requested independently. LinkedIn returned access/rate-limit responses (999 or 429) rather than public profile bodies. The roadmap does not call those HTTP responses public-page proof.

## Research Method

1. Reviewed local portfolio, resume, role-alignment, and project evidence before external discovery.
2. Used web search in separate country/company batches to discover official company, product, career, internship, and role pages.
3. Fetched the official URLs directly and stored HTTP status, final URL, title, and page excerpt.
4. Ran a four-way parallel deep-research pass across the 20 companies, then fetched a second set of primary pages for the claims that could change ranking.
5. Confirmed Apollo organization records through Composio and searched relevant leadership, product, engineering, operations, talent, and commercial functions.
6. Enriched final people with Apollo by ID or exact name plus domain.
7. Excluded stale, former, extrapolated-email, missing-email, missing-LinkedIn, or current-employer-mismatch records.
8. Requested every final LinkedIn URL independently and retained the exact access result.
9. Ranked targets using an analyst priority score across candidate fit, language/working environment, founder/team access, visible entry path, and relocation practicality.

A score is a prioritisation aid, **not** a probability of receiving an offer. A contact is a high-value approach path, **not** proof that the person is currently hiring.

## Active Target Set

### Japan

Kotoba Technologies · LayerX · Algomatic · CADDi · Woven by Toyota · Sakana AI · Mercari · Rakuten · ABEJA · Turing

### Singapore

Tookitaki · Nium · Silent Eight · Carro · Hypotenuse AI · Sea/Shopee · Trax · Endowus · Grab · PatSnap

## Exclusions

- **Active.Ai:** not retained as an active target because the current public company/hiring surface was not strong enough to pass the three-contact gate.
- **Advance Intelligence Group:** not retained because the selected Apollo records did not produce three current recruiting-relevant contacts with verified emails and LinkedIn URLs.
- **Hypotenuse AI:** retained as a founder-outreach target, but its former careers subdomain returned 404 during the direct check; use the live product, blog, and contact pages until a current hiring page is confirmed.
- **Hypotenuse ranking correction:** the reachable YC Product Architect listing is Singapore-located but states “US citizen/visa only”; it was therefore moved to the exploratory end of the Singapore list despite strong profile fit.
- **Carro:** retained because its careers page and Apollo contact surface are usable; two official pages returned 403 to automated HTTP requests and remain access-limited rather than being presented as fully fetched proof.

## Privacy / Publishing Boundary

The central dataset contains business contact details obtained through Apollo for personal recruiting outreach. Review and minimise the raw email layer before publishing the portfolio repository publicly. No message was sent and no external record was modified by this research run.

## Regeneration

Run from `/Users/satyyy/Desktop/PORTFOLIO`:

```bash
python RESEARCH/build_curated_contacts.py
python RESEARCH/validate_linkedin_profiles.py
python RESEARCH/fetch_official_evidence.py
python RESEARCH/build_opportunity_map_data.py
python RESEARCH/emit_data_js.py
python RESEARCH/build_entry_strategy_diagram.py
python RESEARCH/qa_static.py
node --check RESEARCH/roadmap_inline.js
```

For a full browser check, start a local server and run:

```bash
python -m http.server 8123 --directory .
~/.hermes/hermes-agent/venv/bin/python RESEARCH/qa_browser.py
```

The browser verifier covers HTTP and `file://` delivery, Chromium/WebKit, 1440px/768px/390px viewports, filters, dossier expansion, modal focus trapping, progress semantics, print mode, responsive diagrams, contact-card containment, console errors, and horizontal overflow.
