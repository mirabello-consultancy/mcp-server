# Mirabello Consultancy — Investment Migration MCP Server

> The first Model Context Protocol (MCP) server for citizenship- and residency-by-investment.
> Maintained by [Mirabello Consultancy](https://www.mirabelloconsultancy.com) — a Swiss boutique investment-migration advisory (Zurich + Dubai; IMC member, ACAMS certified).

Authoritative, regularly-updated data on **citizenship-by-investment (CBI)** and **residency-by-investment (RBI / golden visa)** programmes — list, compare, estimate total cost for a family, check passport mobility, and book a consultation.

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

## Tools

| Tool | Purpose |
|---|---|
| `list_programmes` | List CBI/RBI programmes, filter by type, budget, region, processing time |
| `get_programme` | Full detail for one programme |
| `compare_programmes` | Compare 2–4 programmes side by side |
| `get_processing_times` | Processing-time estimates |
| `estimate_total_cost` | Indicative total cost for a given family |
| `recommend_programmes` | Ranked shortlist for a client profile |
| `check_visa_free` | Passport mobility (visa-free count, key destinations) |
| `book_consultation` | Book a free consultation (requires explicit consent) |

Also exposes an MCP resource (`mirabello://programmes/all`) and an advisor prompt.

## REST mirror (for non-MCP clients)

A read-only HTTP mirror is available under `/v1`, documented by an OpenAPI spec:

- OpenAPI: <https://mcp.mirabelloconsultancy.com/v1/openapi.json>
- Developer docs: <https://mcp.mirabelloconsultancy.com/developers>
- Discovery: `/.well-known/mcp.json`, `/.well-known/ai-plugin.json`, `/server.json`

## Disclaimer

Figures are **indicative** and subject to change; this server provides general information only and is **not** legal, financial, tax, or immigration advice, nor an offer or solicitation. Programmes are operated and governed solely by the respective sovereign governments. © Mirabello Consultancy Ltd. Terms: <https://www.mirabelloconsultancy.com/ai>
