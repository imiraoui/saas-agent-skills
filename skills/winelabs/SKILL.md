---
name: winelabs
description: Resolve wines to Wine Labs IDs or LWIN and compare current merchant offers, reference values, and historical auction or exchange observations. Use for wine pricing, market comparisons, or cellar matching.
license: MIT-0
metadata:
  homepage: https://winelabs.ai/
  version: "1.0.0"
---

# Wine Labs

[Wine Labs](https://winelabs.ai/) provides wine identity, prices, and market data. Connect the user through OAuth to `https://chat.wine-labs.com/mcp`; see the [agent setup guide](https://winelabs.ai/agents). Consult the connected tool catalog first. Use `search_winelabs_endpoints` to discover the supported route and argument schema, then `fetch_winelabs_data` for the selected route, if the connector exposes those tools. [REST API docs](https://winelabs.ai/api/docs) cover direct integrations and route entitlements.

## Resolve before pricing

1. Resolve the producer, cuvée, vintage, and bottle size with the matching operation (look up `match_to_lwin`). Keep the canonical label and returned Wine Labs ID or most specific LWIN for downstream calls. A base identity is not a vintage or bottle-size match. If matching is ambiguous, ask for the label details or report separate candidates.
2. Ask for the right market evidence. Current merchant offers are asking prices; completed auction and exchange trades are observations; a Wine Labs reference value is an estimate. Keep these separate and compare only the relevant geography, dates, and bottle formats. Distinguish hammer from all-in auction prices where the source specifies the basis.
3. Report original currency and quantity, any conversion or per-bottle normalization, observation dates, venue or merchant, and source links or IDs when returned. Keep case packs, different formats, and materially different conditions separate. Label sparse evidence instead of filling gaps with another vintage or size.

For inventories, discover the supported batch or cellar workflow before sending data. Scope the batch and check expected credit usage before metered calls at scale. Keep unresolved rows for review. If a market or route needs an entitlement, surface the limitation rather than substituting an unrelated market.

Example: “Find the latest US offers for Château Margaux 2015 in 750 mL, then show recent comparable auction results in a separate table.”
