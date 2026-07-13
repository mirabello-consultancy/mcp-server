# Mirabello Consultancy — Investment Migration & Wealth-Protection MCP Server

> The first Model Context Protocol (MCP) server for citizenship- and residency-by-investment — now extended into tax residency, wealth-protection structuring, and qualifying real estate.
> Maintained by [Mirabello Consultancy](https://www.mirabelloconsultancy.com) — a Swiss boutique investment-migration advisory (Zurich + Dubai; IMC member, ACAMS certified).

Authoritative, regularly-updated, source-cited data across five layers: **citizenship-by-investment (CBI)** and **residency-by-investment (RBI / golden visa)** programmes, **country immigration pathways** (skilled-work, digital-nomad, retirement, descent, and more), **HNWI tax & wealth-protection** (income/CGT/inheritance/wealth tax, trusts, succession, treaties), **qualifying investment real estate**, and **consultation / briefing hand-off** to a licensed advisor.

## Connect (remote, no install)

Streamable-HTTP, stateless JSON-RPC 2.0:

```
https://mcp.mirabelloconsultancy.com/
```

Add to an MCP client config:

```json
{
  "mcpServers": {
    "mirabello": { "url": "https://mcp.mirabelloconsultancy.com/", "transport": "streamable-http" }
  }
}
```

## Tools (44)

### Programme data — CBI / RBI
| Tool | Purpose |
|---|---|
| `list_programmes` | List CBI/RBI programmes, filter by type, budget, region, processing time |
| `get_programme` | Full detail for one programme, incl. its Mirabello Index score + rank |
| `compare_programmes` | Compare 2–4 programmes, or the canonical two-programme Index artefact |
| `get_processing_times` | Processing-time estimate for one programme or all |
| `estimate_total_cost` | Total cost for a given family: investment + govt/DD fees + add-ons |
| `recommend_programmes` | Ranked shortlist for a client profile (budget, family, timeline, tax goal) |
| `check_visa_free` | Passport mobility for a programme — visa-free count, key destinations |
| `get_index` | The Mirabello Investment Migration Index — composite 0–100 ranking |
| `get_recent_changes` | Recent programme changes, official-source field-level diffs |
| `get_about` | Mirabello track record, credentials, offices, languages |
| `get_passport_renewal` | CBI passport-renewal facts for 6 Caribbean/Pacific programmes |
| `check_eligibility` | Which programmes a nationality can realistically apply to |
| `get_document_checklist` | Standard document checklist for a programme application |
| `estimate_timeline` | Stage-by-stage expected timeline for a programme |

### Country & pathway intelligence
| Tool | Purpose |
|---|---|
| `get_country` | All screened immigration pathways for a country (work, nomad, retirement, descent, study, family…) |
| `get_provenance` | Citation-first source + confidence + freshness for a country's pathway facts |
| `query_graph` | Relational query over the programme/country/bloc/authority knowledge graph |
| `plan_path` | The Mirabello Freedom Compass — origin-aware migration path planner |
| `find_pathways` | Which countries offer a given pathway (e.g. digital-nomad, skilled-work) |

### Tax & wealth-protection
| Tool | Purpose |
|---|---|
| `get_country_tax` | HNWI tax profile — income, CGT, inheritance, wealth tax, CRS, special regimes |
| `find_low_tax` | Find countries by tax criteria (no income/inheritance/wealth tax, territorial, non-CRS, crypto-friendly) |
| `find_trust_jurisdictions` | Trust & foundation jurisdictions ranked by asset-protection strength |
| `find_charity_jurisdictions` | Philanthropic-structure jurisdictions (foundations, DAFs, charitable trusts, waqf) |
| `compare_treaty_position` | Double-tax-treaty position for a relocation corridor |
| `withholding_map` | Treaty withholding rates (dividends/interest/royalties) for a corridor |
| `flag_cfc_poe_risk` | CFC/GAAR/POEM/exit-tax flags for a jurisdiction |
| `residence_evidence_checklist` | Tax-residence tests + evidence factors for a jurisdiction |
| `build_sow_pack` | Source-of-wealth / source-of-funds evidence pack by wealth-origin type |
| `forced_heirship_risk` | Forced-heirship / reserved-share position per jurisdiction |
| `matrimonial_regime_screen` | Default matrimonial-property regime per jurisdiction |
| `succession_conflict_map` | Cross-border succession conflict-of-laws position |
| `compare_scenarios` | Side-by-side tax/structure/succession comparison of 2–8 jurisdictions |
| `compliance_checklist` | Reporting obligations (FATCA, CRS, CARF/DAC8, DAC6, PEP) from stated flags |
| `get_mobility_optionality` | Strategic residence/citizenship routes per jurisdiction |
| `get_digital_gov_progress` | CBDC/stablecoin/digital-ID status per country |
| `get_wealth_atlas` | Mirabello Wealth-Protection Atlas — per-pillar 0–100 sub-indices |
| `get_wealth_index` | Client-weighted composite over the Atlas pillars |

### Real estate
| Tool | Purpose |
|---|---|
| `search_properties` | Filterable search of CBI/RBI-qualifying investment property |
| `get_property` | Full detail for one property listing |
| `get_availability_updates` | Recently re-verified listings since a given date |
| `create_enquiry` | Route a buyer enquiry to Mirabello (broker of record) — requires consent |

### Consultation & engagement
| Tool | Purpose |
|---|---|
| `book_consultation` | Book a free consultation (requires email + explicit consent) |
| `generate_briefing` | Personalised shortlist + shareable 90-day briefing URL |
| `subscribe_changes` | Subscribe to verified programme-change alerts (webhook or email) |

Also exposes MCP resources (`mirabello://programmes/all`, `mirabello://index`, `mirabello://track-record`) and an `investment_migration_advisor` prompt.

## REST mirror (for non-MCP clients)

A read-only HTTP mirror is available under `/v1`, documented by an OpenAPI spec:

- OpenAPI: <https://mcp.mirabelloconsultancy.com/v1/openapi.json>
- Developer docs: <https://mcp.mirabelloconsultancy.com/developers>
- Discovery: `/.well-known/mcp.json`, `/.well-known/ai-plugin.json`, `/server.json`

## Disclaimer

Figures are **indicative** and subject to change; this server provides general information only and is **not** legal, financial, tax, or immigration advice, nor an offer or solicitation. Programmes are operated and governed solely by the respective sovereign governments. © Mirabello Consultancy Ltd. Terms: <https://www.mirabelloconsultancy.com/ai>
