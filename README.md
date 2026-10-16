# Black Business Directory

A nationwide, interactive directory of Black-owned businesses: storefronts, B2B and professional-service firms, federal contractors, and companies organized by sector ETF. Coverage is deepest in the DC–Baltimore region today and grows from there.

**Live:** https://alxndrhq.github.io/black-business-directory/

## Views

- **Map** (home): every listing, clustered, with popups and directions. Click a category chip to show only that category; click more chips to add them, or **All** to reset. Searching zooms the map to the results. Categories include consumer storefronts (restaurants, beauty & barber, retail, fitness, …) and B2B:
  - **Companies**: profiled companies, tagged with their sector ETF (search "XLK", "XLI", …), linked to the owner's dossier.
  - **Professional Services**: law, accounting, insurance, real estate, consulting and other firms with a commercial office.
  - **Federal Contractors**: firms self-certified "Black American Owned" in SAM.gov with federal contracts FY22–26 (USAspending), with their top NAICS line and contract total.
  The **Owners** layer pins each profile to its home base.
- **Owners**: a card for every owner, grouped by sector ETF (XLE, XLB, XLI, XLY, XLP, XLV, XLF, XLK, XLC, XLU, XLRE). Use the Sector filter, or the Web view's "By Sector" layout, to see the Black-owned companies in each sector, B2B firms included.
- **Overlaps**: businesses and institutions shared by two or more owners.
- **Web**: a network graph of owners, their businesses and the ties between them (family, deals, mentorship, civic work). Click any node for a dossier.

The directory is present-day only: living owners and businesses that still operate. Filters for region (Washington DC, Baltimore, National), size tier and sector apply to the owner views.

## Data

| File | What it holds |
|---|---|
| `index.html` | The whole app. Owner profiles and business entities are embedded between `/*DATA-START*/` and `/*DATA-END*/`. |
| `places.json` | Pre-geocoded coordinates, the researched `additions` listings (with owner, note and source link), and a snapshot of the Google Sheet. |

The Map tab reads the [community Google Sheet](https://docs.google.com/spreadsheets/d/1Qqolc72-Xw_KKCM216aMCBodEKLUuuyeSSbC2dbcb0g/edit) live on every visit. About 670 researched listings in `places.json` are merged in beside it; a sheet row for the same business (same name and street address) takes precedence. New sheet rows are geocoded in the visitor's browser.

### Adding a business

- **Fastest:** add a row to the Google Sheet. It shows up on the map on the next page load.
- **In the repo:** append an object to `additions` in `places.json`, and add its `[lat, lng, "street"]` under `geo` using the same lowercase `key`.

### Adding an owner

Append a profile (and an entity for each business) to the embedded dataset in `index.html`. The format is documented in the comment just above `EMBEDDED_DATA`. Set `category` to `"Washington, DC"` or `"Baltimore"`.

Profiles and listings come from public sources linked in each dossier or popup. Confirm hours and locations with each business before you visit.
