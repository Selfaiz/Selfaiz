<h1 align="center">Smail El Faiz</h1>

<p align="center"><b>Systems built for compliance and durability.</b></p>

<p align="center">
  <sub>ERP &amp; finance · banking &amp; tax integration · fleet telematics · document AI · mobile</sub><br/>
  <sub>Rabat, Morocco · FR / EN</sub>
</p>

<br/>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/schematic-dark.svg">
    <img src="assets/schematic-light.svg" width="1000" alt="System schematic in four layers — data sources, ingestion, business rules, interfaces — with an audit trail running under every layer.">
  </picture>
</p>

<br/>

I build and maintain back-office systems for regulated industries — the parts of a business that have to be correct rather than pretty: money, positions, documents, permissions.

Most of that work is private, so there are no screenshots here. What I can show is how the systems are built.

### How I work

Three modes, often on the same system. **Maintaining** software already in production — incidents, corrective and evolutive maintenance, user support. **Building** — new modules, features and platforms. **Integrating** with systems nobody controls — banks, tax authorities, GPS hardware, messaging providers, the system being replaced.

I started on the maintenance side of an ERP in production before extending it. That order teaches early which shortcuts become incidents, what an audit trail is actually for, and why the boring parts of a system are the ones that keep it alive.

### Where

| Sector | The design problem | How I approach it |
|---|---|---|
| ERP & finance | Money moves through a chain of documents that arrive late, out of order or twice — and every total must still reconcile | Append-only document history; reconciliation as a first-class read model |
| Banking & tax integration | Formats you don't control, from systems that aren't always available, where one mismatched line is a compliance matter | Keep the original file as evidence; idempotent ingestion; deterministic matching with a human queue for the ambiguous cases |
| Fleet telematics | One continuous stream of positions serving three very different reads: live map, playback, reporting | Separate ingestion from query — time-series for raw data, a current-state store for live views, pre-aggregated trips for reports |
| Document AI (OCR / GED) | Extraction is confidently imperfect, and the last few percent carry most of the cost | Confidence thresholds with human review built into the product; extraction as a layer over an immutable original |
| Messaging gateways | Delivery is asynchronous and providers behave differently | Outbox pattern with idempotent sends; "sent" and "delivered" tracked as distinct facts |
| Portals & access control | Many roles, many tenants, one back-office | Authorise on resource · action · scope; tenancy enforced at the data layer, auditable |
| Migration & integration | The incumbent system can't stop while it's being replaced | Strangler pattern — run both in parallel, reconcile continuously, migrate reads before writes |

### Stack, briefly

**Laravel** for business systems a team maintains for years · **TypeScript / React** for back-office interfaces · **Python** for OCR, data and scraping work · **Flutter** for the mobile clients · **PostgreSQL / MySQL / Redis**, boring on purpose · **Docker + GitHub Actions** from day one.

### Elsewhere

[LinkedIn](https://www.linkedin.com/in/smailelfaiz/) · [smailelfaiz@gmail.com](mailto:smailelfaiz@gmail.com)

<!-- Add · [smailelfaiz.com](https://smailelfaiz.com) the day the site is live. Never leave a dead link on this page. -->
