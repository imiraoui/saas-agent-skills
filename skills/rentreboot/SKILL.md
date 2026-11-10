---
name: rentreboot
description: Compare NYC neighborhood asking rents, find renter guides, or review the user's RentReboot apartment alerts and saved search. Use for NYC rental research and account tasks through the RentReboot connector.
license: MIT-0
metadata:
  homepage: https://rentreboot.com/
  version: "1.0.0"
---

# RentReboot

[RentReboot](https://rentreboot.com/) publishes NYC renter guides and neighborhood asking-rent data, and delivers apartment alerts to subscribers. Prefer the connected RentReboot tools when available. The public Streamable HTTP MCP endpoint is `https://rentreboot.com/api/mcp`; no sign-in is needed for public tools. See the [server card](https://rentreboot.com/.well-known/mcp/server-card.json) and [OAuth documentation](https://rentreboot.com/auth.md).

## Research a neighborhood

- Use `list_neighborhoods` to resolve the neighborhood and borough and `get_rent_data` for the requested bedroom count. For comparisons, use the same bedroom count and reporting period. Report the median, spread if available, sample size, period, and source. These are asking-rent observations; a small sample or an unreported bedroom category is not proof of a market price.
- Use `search_guides` to find relevant guides and `get_guide` to read a match. Link to the original guide. If MCP is unavailable, use the public [rent data](https://rentreboot.com/average) or [renter guides](https://rentreboot.com/guides).

## Work with the renter's account

Let the user sign in through the client's OAuth flow for personal tools. Use the scopes and tools the client actually offers. Use `list_alerted_listings` for alerts already sent and `get_search_preferences` to understand the saved criteria. `list_historical_matches` (called `list_upcoming_matches` in some clients) returns historical matches for planning; do not describe them as active or future inventory. Verify current availability against the original listing. If a connected client exposes a separate live search tool, label those results separately from alerts and historical matches.

If a client exposes a write tool, confirm the specific change before updating preferences, pausing or resuming alerts, or changing an alerted listing's tracking state. Recording “contacted” or “applied” does not contact a broker or submit an application. Keep private account links and OAuth credentials out of the response.

Example: “Compare one-bedroom asking rents in Astoria and Sunnyside. Show the sample sizes and link to the underlying rent pages.”
