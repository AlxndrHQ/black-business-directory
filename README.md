# Black Business Directory · DC & Baltimore

An interactive directory of Black-owned businesses and Black business owners in Washington, DC, Baltimore and the suburbs between them.

**Live:** https://alxndrhq.github.io/black-business-directory/

## Views

- **Web**: a network graph of owners, their businesses and the ties between them (family, deals, mentorship, civic work). Click any node for a dossier.
- **Owners**: a card for every owner, grouped by sector.
- **Overlaps**: businesses and institutions shared by two or more owners.
- **Map**: Black-owned storefronts across DC and Baltimore, with category filters, popups and directions. The **Owners** layer pins each profile to its home base.

Filters for era, region (Washington DC, Baltimore, National Legacy), size tier and sector apply to every view.

## Data

| File | What it holds |
|---|---|
| `index.html` | The whole app. Owner profiles and business entities are embedded between `/*DATA-START*/` and `/*DATA-END*/`. |
| `places.json` | Pre-geocoded coordinates, the researched `additions` listings (with owner, note and source link), and a snapshot of the Google Sheet. |

The Map tab reads the [community Google Sheet](https://docs.google.com/spreadsheets/d/1Qqolc72-Xw_KKCM216aMCBodEKLUuuyeSSbC2dbcb0g/edit) live on every visit. Researched listings in `places.json` are merged in beside it, and a sheet row with the same name and city takes precedence. New sheet rows are geocoded in the visitor's browser.

### Adding a business

- **Fastest:** add a row to the Google Sheet. It shows up on the map on the next page load.
- **In the repo:** append an object to `additions` in `places.json`, and add its `[lat, lng, "street"]` under `geo` using the same lowercase `key`.

### Adding an owner

Append a profile (and an entity for each business) to the embedded dataset in `index.html`. The format is documented in the comment just above `EMBEDDED_DATA`. Set `category` to `"Washington, DC"` or `"Baltimore"`.

Profiles and listings come from public sources linked in each dossier or popup. Confirm hours and locations with each business before you visit.
