# Global Escape Research Ledger

## Purpose

This folder maintains a job-first relocation route for a founder-side AI systems, product, and operations builder. The route tests a country through useful work before a foreign Master’s commitment.

Canonical presentation: [`../GLOBAL_ESCAPE_ROADMAP.html`](../GLOBAL_ESCAPE_ROADMAP.html)

Central data layer: [`7_nation_opportunities.json`](RESEARCH/7_nation_opportunities.json)

Supported opportunity presentation: [`FULLY_FUNDED_OPPORTUNITIES.html`](FULLY_FUNDED_OPPORTUNITIES.html)

Decision diagram: [`7_nation_decision_diagram.html`](RESEARCH/7_nation_decision_diagram.html)

Parallel company research packet: [`delegated_company_research.json`](delegated_company_research.json)

Primary checks for the delegated packet: [`delegated_primary_checks.json`](delegated_primary_checks.json)

Editable strategy diagram: [`../GLOBAL_ESCAPE_ENTRY_STRATEGY.excalidraw`](../GLOBAL_ESCAPE_ENTRY_STRATEGY.excalidraw)

## Current Curation (v2, 28 August 2026)

- **Countries:** Estonia, Japan, UAE, Germany, Netherlands, Singapore, Russia.
- **Qualifying routes:** 14.
- **Support gate:** every retained route has at least one official support item (tuition, stipend/salary, travel, housing, insurance, visa or work authorisation).
- **Official URL reachability:** 31/33 unique official URLs returned HTTP 200; one Embassy of Japan India page returned 403 and the Estonia application portal timed out to the checker. Both remain linked and disclosed.
- **Apollo:** 11 organization identity checks. Apollo is not treated as proof of funding, hiring, salary, or visa sponsorship.
- **Old 34-card list:** superseded. Cards without explicit support evidence, stale deadlines, or unsupported relocation claims were removed or moved to exclusions.

## Research Method

1. Reviewed local portfolio, resume, role-alignment, and project evidence before external discovery.
2. Used web search in separate country/company batches to discover official company, product, career, internship, and role pages.
3. Fetched the official URLs directly and stored HTTP status, final URL, title, and page excerpt.
4. Ran parallel live research across seven country lanes and independently checked the official programme pages.
5. Verified funding, deadlines, eligibility and support boundaries against government/university sources.
6. Used Apollo through Composio for organization identity and employer watchlist cross-checks only.
7. Excluded stale, unsupported, no-funding, unverified, or past-deadline items from the qualifying list; preserved them in the exclusion ledger.
8. Ranked routes using technical fit, eligibility, support strength, deadline actionability, language, route realism and country risk.

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
