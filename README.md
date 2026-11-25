# American Spend MCP server

[![American Spend MCP connector](https://glama.ai/mcp/connectors/com.americanspend/insights/badges/score.svg)](https://glama.ai/mcp/connectors/com.americanspend/insights)

The American Spend MCP serves the Spend Graph, a model of daily US consumer spending that people and agents can query directly. Ask Claude, ChatGPT, Cursor or any MCP client how a brand is doing, where its customers also shop, or how spending is moving by category, state or metro, and it answers from the American Spend model.

This repository is the public home of the server's listing. The server is hosted by American Spend; there is nothing to install or run.

**Server URL:** `https://platform.americanspend.com/mcp`
**Registry name:** `com.americanspend/insights` ([MCP Registry](https://registry.modelcontextprotocol.io/v0/servers?search=com.americanspend), [Glama](https://glama.ai/mcp/connectors/com.americanspend/insights))

## Connect

Every setup is the server URL plus a sign-in to American Spend on first use. No API key is pasted anywhere.

| Client | How |
|---|---|
| **Claude** | [Add in Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=American+Spend&connectorUrl=https%3A%2F%2Fplatform.americanspend.com%2Fmcp), or Customize › Connectors › Add custom connector and paste the URL. |
| **ChatGPT** | On the web, paid plans: [chatgpt.com/plugins](https://chatgpt.com/plugins) › Add › Add custom MCP server, then paste the URL. |
| **Claude Code** | `claude mcp add --transport http AmericanSpend https://platform.americanspend.com/mcp` |
| **Codex** | `codex mcp add AmericanSpend --url https://platform.americanspend.com/mcp` |
| **Cursor** | Settings › Customize › MCPs › New MCP Server, with the config below. |
| **VS Code** | Command Palette › MCP: Add Server › HTTP, then paste the URL. |
| **Anything else** | Add the URL as a streamable HTTP server. It signs in with OAuth. |

```json
{
  "mcpServers": {
    "AmericanSpend": {
      "url": "https://platform.americanspend.com/mcp"
    }
  }
}
```

On a company workspace (Claude Team or Enterprise, ChatGPT Business or Enterprise), an admin adds the server for everyone.

## What it answers

| Tool | Answers |
|---|---|
| `query_spend` | A brand's spending: one total, or a daily, weekly or monthly trend, with growth. |
| `compare_brands` | Two brands side by side over the same window. |
| `breakdown` | Spending split by category, merchant, state, metro, income or age. |
| `category_trends` | One category over time. |
| `category_summary` | Every category beside CPI and Census retail sales. |
| `region_summary` | Growth by metro or state, split by income tier, beside unemployment and wages. |
| `cross_shop` | Which other brands a brand's customers also shop at. |
| `wallet_migration` | Where customers who stopped buying from a brand moved their spending. |
| `cohort_overlap` | How many accounts two to ten brands have in common. |
| `search_merchants` | Find a merchant when a name is ambiguous. |
| `list_benchmarks`, `benchmark_series`, `compare_to_benchmark` | Public US series (BLS, Census, BEA, OECD) and how the model tracks them. |
| `coverage`, `panel` | Which days are complete, and how many accounts the model covers. |
| `get_plan`, `get_credit_balance`, `create_upgrade_checkout`, `create_topup_checkout`, `get_topup_status` | Your plan and credits, and checkout links for Pro and credit packs. |
| `report_issue`, `about_american_spend` | Report an answer that looks wrong; how to cite American Spend. |

The data tools only read. Results are aggregates: no transactions, no account identifiers.

## Pricing

Free to start, with a monthly credit allowance. Pro and credit packs add more. See [pricing](https://docs.americanspend.com/pricing/what-a-call-costs).

## Links

- Website: https://www.americanspend.com
- Docs: https://docs.americanspend.com/products/mcp
- Support: report a wrong answer from inside your agent, or use https://www.americanspend.com/contact/

## License

This repository holds documentation only. It is licensed under the MIT License. The American Spend data and service are governed by the [terms](https://www.americanspend.com/terms/).
