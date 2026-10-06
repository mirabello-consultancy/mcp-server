# Mirabello Immigration Intelligence: MCP Server

> The first Model Context Protocol (MCP) server for citizenship- and residency-by-investment, grown into a global relocation, tax-residency and wealth-protection data layer.
> Maintained by [Mirabello Consultancy](https://www.mirabelloconsultancy.com), a Swiss boutique investment-migration advisory (Zurich, Dubai, Hong Kong SAR; IMC member, ACAMS certified).

**63 tools · 98 investment-migration programmes · 194 countries · 1,229 verified immigration pathways · 199 × 199 visa matrix · 14 statute-read naturalisation regimes**

Every figure is sourced: official government sources first, corroborated where possible, with verification dates and confidence returned alongside the data. Where a fact cannot be verified, the server says so instead of guessing.

## Connect (remote, no install)

Streamable HTTP, stateless JSON-RPC 2.0, no API key:

```
https://mcp.mirabelloconsultancy.com/
```

MCP client config:

```json
{
  "mcpServers": {
    "mirabello": { "url": "https://mcp.mirabelloconsultancy.com/", "transport": "streamable-http" }
  }
}
```

Also listed on the official MCP Registry, Glama, PulseMCP, mcp.so and Smithery.

### In Grok

Grok supports custom MCP connectors for every user: go to [grok.com/connectors](https://grok.com/connectors), click **New Connector**, choose **Custom** and paste `https://mcp.mirabelloconsultancy.com/`. Grok Business and Enterprise admins add it once under console.x.ai, Grok Business, Connectors. For Grok Build, this repo is also a plugin (`.mcp.json` + `.grok-plugin/plugin.json`).

### In Claude and ChatGPT

Claude: Settings, Connectors, Add custom connector, paste the address above. ChatGPT: [Mirabello Immigration Intelligence in the GPT Store](https://chatgpt.com/g/g-6a5cafe6f6188191bae23f9c77f9e6bf-mirabello-immigration-intelligence).

## What you can ask

- "I am a Nigerian entrepreneur with USD 300,000. Which second citizenship fits my family of four, and what does it cost?"
- "Which countries offer a digital nomad visa, and what income do they require?"
- "What is the fastest way for a Brazilian to reach an EU passport?"
- "I am German and want to retire in Portugal. Do I need a visa?"
- "Where can a Pakistani passport travel visa-free?"
- "Compare the tax position of moving from Germany to the UAE versus Switzerland."

## Tools (63)

59 tools are read-only. 4 act on the user's behalf (`book_consultation`, `generate_briefing`, `subscribe_changes`, `create_enquiry`), and only with explicit consent.

### Investment migration: CBI / RBI programmes (14)
| Tool | Purpose |
|---|---|
| `list_programmes` | List citizenship- and residency-by-investment programmes with every investment route and its minimum; filter by type, budget, region, processing time |
| `get_programme` | Full record for one programme: routes, fees, family rules, processing, mobility, tax, Index score, sources |
| `compare_programmes` | Side-by-side comparison of 2 to 4 programmes |
| `get_processing_times` | Processing time for one programme or all |
| `estimate_total_cost` | Itemised total for a given family: investment, government and due-diligence fees |
| `recommend_programmes` | Ranked shortlist for a client profile (budget, family, timeline, mobility, tax goal) |
| `check_visa_free` | Passport mobility of a programme: visa-free count and key destinations |
| `get_index` | The Mirabello Investment Migration Index, a composite 0 to 100 ranking |
| `get_recent_changes` | Recent programme changes with field-level diffs and official sources |
| `check_eligibility` | Which programmes a nationality can realistically apply to |
| `get_document_checklist` | Standard document checklist for an application |
| `estimate_timeline` | Stage-by-stage expected timeline |
| `get_passport_renewal` | Passport-renewal rules for CBI countries |
| `get_about` | Mirabello track record, credentials, offices, languages |

### Countries, pathways and naturalisation (6)
| Tool | Purpose |
|---|---|
| `get_country` | Every verified pathway for a country: skilled work, digital nomad, retirement, study, family, descent, investment, EU free movement; pass `nationality` to tailor it |
| `find_pathways` | Which countries offer a given pathway, with income thresholds and requirements |
| `find_fastest_citizenship` | Naturalisation periods and nationality-based fast tracks read from the enacted statute; one call ranks a whole bloc (e.g. `bloc: "EU"`) |
| `plan_path` | The Mirabello Freedom Compass: origin-aware planner from a person's current citizenship and goal to ranked routes |
| `get_provenance` | Citation-first provenance for a country's facts: source, tier, verification date, confidence |
| `query_graph` | Relational query over the programme, country, bloc and authority knowledge graph |

### Travel and entry (3)
| Tool | Purpose |
|---|---|
| `check_visa_requirement` | Visa requirement for one nationality to one destination, with maximum stay |
| `list_visa_free_destinations` | Every destination for one passport, grouped: visa-free, on arrival, e-visa, electronic authorisation, visa required |
| `get_entry_requirements` | Passport-validity and entry rules of a destination |

### Relocation practicalities (6)
| Tool | Purpose |
|---|---|
| `get_capital_controls` | Whether, and how much, money may legally leave a country |
| `get_nonresident_banking` | Bank-account access for non-resident individuals and companies |
| `get_property_law` | Real-estate rules for foreign buyers |
| `get_name_change` | Legal name-change rules |
| `get_foundation_rules` | Charitable and private foundation and trust rules |
| `get_emigration_flows` | Official emigration statistics by destination (German Destatis data) |

### Tax and wealth protection (19)
| Tool | Purpose |
|---|---|
| `get_country_tax` | HNWI tax profile: income, capital gains, inheritance, wealth tax, CRS, special regimes |
| `find_low_tax` | Countries by tax criteria (no income, inheritance or wealth tax, territorial, crypto treatment) |
| `compare_treaty_position` | Double-tax-treaty position for a relocation corridor |
| `withholding_map` | Treaty withholding rates for dividends, interest and royalties |
| `residence_evidence_checklist` | Tax-residence tests and the evidence that proves them |
| `flag_cfc_poe_risk` | CFC, GAAR, place-of-effective-management and exit-tax flags |
| `compliance_checklist` | Reporting obligations (FATCA, CRS, CARF/DAC8, DAC6, PEP) for a stated profile |
| `build_sow_pack` | Source-of-wealth and source-of-funds evidence pack by wealth origin |
| `find_trust_jurisdictions` | Trust and foundation jurisdictions by asset-protection strength |
| `find_charity_jurisdictions` | Jurisdictions for philanthropic structures |
| `forced_heirship_risk` | Forced-heirship and reserved-share position |
| `matrimonial_regime_screen` | Default matrimonial-property regime |
| `succession_conflict_map` | Cross-border succession conflict of laws |
| `choice_of_law_options` | Which law may govern succession, matrimonial property and divorce |
| `compare_scenarios` | 2 to 8 jurisdictions across every wealth-protection dimension at once |
| `get_mobility_optionality` | The lawful residence and citizenship routes a jurisdiction offers |
| `get_digital_gov_progress` | CBDC, stablecoin and digital-ID status |
| `get_wealth_atlas` | Mirabello Wealth-Protection Atlas: per-pillar sub-indices (0 to 100) |
| `get_wealth_index` | Client-weighted composite over the Atlas pillars |

### Global structuring (8)
| Tool | Purpose |
|---|---|
| `plan_global_setup` | One origin-aware answer combining residence, company, banking and tax |
| `get_structuring_roster` | Curated company-formation jurisdictions from a full country screen |
| `get_structuring_playbook` | Recommended setups by customer market |
| `get_company_formation` | Full formation profile for one structure |
| `find_formation_jurisdictions` | Filter formation profiles by constraints |
| `compare_formation` | Compare 2 to 6 formation structures |
| `get_banking_access` | Non-resident banking landscape per jurisdiction |
| `get_regulator_registry` | Regulators for tax, companies, accounting, treaties and banking |

### Real estate (4)
| Tool | Purpose |
|---|---|
| `search_properties` | Investment property that qualifies for a CBI or RBI programme |
| `get_property` | Full detail for one listing |
| `get_availability_updates` | Recently re-verified listings |
| `create_enquiry` | Route a buyer enquiry to Mirabello (requires consent) |

### Consultation (3)
| Tool | Purpose |
|---|---|
| `book_consultation` | Book a free consultation (requires email and explicit consent) |
| `generate_briefing` | Personalised shortlist with a private 90-day briefing page |
| `subscribe_changes` | Verified programme-change alerts |

### Prompts and resources

- Prompts: `investment_migration_advisor`, `shortlist_for_client`, `verify_a_figure`, `explain_a_refusal`
- Resources: `mirabello://programmes/all`, `mirabello://programmes/{id}`, `mirabello://index`, `mirabello://track-record`, `ui://mirabello/freedom-compass.html`

## REST mirror (for non-MCP clients)

A read-only HTTP mirror under `/v1`, documented by OpenAPI (copy in this repo: `openapi.json`):

- OpenAPI: <https://mcp.mirabelloconsultancy.com/v1/openapi.json>
- Developer docs: <https://mcp.mirabelloconsultancy.com/developers>
- Discovery: `/.well-known/mcp.json`, `/server.json`, `/llms.txt`

## Data standards

- Official government sources first; corroboration where possible; figures that cannot be verified are withheld or flagged, never estimated.
- Every record carries its source, verification date and confidence; `get_provenance` exposes them.
- Closed, paused and announced-but-not-in-force programmes stay listed and are clearly marked, so agents get the correct answer instead of an outdated one.
- The server never helps conceal assets or income from tax authorities; CRS and FATCA reporting applies.

If this server is useful to you, a GitHub star helps other developers find it.

## Disclaimer

Figures are indicative and subject to change. This server provides general information only and is not legal, financial, tax or immigration advice, nor an offer or solicitation. Programmes are operated and governed solely by the respective governments. © Mirabello Consultancy Ltd. Terms: <https://www.mirabelloconsultancy.com/ai>
