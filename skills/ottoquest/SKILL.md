---
name: ottoquest
description: Find used cars in the US, check a VIN or market value, and compare comparable listings with OttoQuest. Use for vehicle shopping, model safety research, or existing OttoQuest deal alerts.
license: MIT-0
metadata:
  homepage: https://ottoquest.com/
  version: "1.0.0"
---

# OttoQuest

[OttoQuest](https://ottoquest.com/) compares US vehicle listings with estimated market values. Connect to `https://ottoquest.com/api/mcp` over Streamable HTTP and let the user sign in through the client's OAuth flow. See [MCP setup](https://ottoquest.com/mcp). Use the connected tool schemas to check availability. Without a connection, use public [listings](https://ottoquest.com/listings) or [market research](https://ottoquest.com/market/research) and report any gaps.

## Find or evaluate a car

- **Shopping:** Use `find_cars` with the stated filters. For example, `{"cars":["Toyota RAV4"],"near":"Austin, TX","radius":50,"max_price":30000,"deals":true}` searches within 50 miles for below-market listings. Use `clean` only when the shopper wants clean title and no reported accidents. Explain any unmatched model names or any filter relaxation.
- **Specific VIN:** Use `car_by_vin` with the full 17-character VIN. Include actual mileage and US state when known. Separate estimated value, current listings, reported history, and recalls. Prior sightings or sales may depend on the account plan.
- **No VIN:** Use `value_car` with model or trim and model year; supply mileage, state, and known history where available. If there are too few comparables, say so. For a model-level question use `market_research` or `model_safety` as appropriate.

For a shortlist, include asking price, estimated value or range, gap to market, mileage, location, and a returned listing link. Use the evidence counts or basis returned by the tool. A listed price can exclude taxes and fees, a listing can go stale, and missing history is unknown. Confirm availability and the out-the-door price with the listing source before relying on either.

Use `list_deal_alerts` to review existing alerts. Before creating or deleting an alert, confirm the search and cadence or the exact alert to remove. Availability of instant alerts depends on the user's plan.

Example: “Find three RAV4s below market around Austin under $30,000, and show the price and mileage tradeoffs.”
