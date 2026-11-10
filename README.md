# Agent skills for PennyOCR, OttoQuest, Wine Labs, and RentReboot

Four [Agent Skills](https://agentskills.io/) that teach an assistant when to use each product, how to connect, and how to interpret its results. The skills contain instructions only. Install them in Codex, Claude Code, Cursor, or another compatible client, then connect the relevant service when needed.

| Skill | What it helps with | Product and setup |
| --- | --- | --- |
| [PennyOCR](skills/pennyocr/SKILL.md) | Extract page text and tables from PDFs and images; estimate and cap URL OCR costs. | [PennyOCR](https://www.pennyocr.com/) · [MCP](https://www.pennyocr.com/mcp/) · [API](https://www.pennyocr.com/docs/) |
| [OttoQuest](skills/ottoquest/SKILL.md) | Find US used cars, look up a VIN, and compare asking prices with market estimates. | [OttoQuest](https://ottoquest.com/) · [MCP](https://ottoquest.com/mcp) |
| [Wine Labs](skills/winelabs/SKILL.md) | Resolve wines and compare merchant offers, reference values, and historical trades. | [Wine Labs](https://winelabs.ai/) · [MCP](https://winelabs.ai/agents) · [API](https://winelabs.ai/api/docs) |
| [RentReboot](skills/rentreboot/SKILL.md) | Research NYC asking rents and renter guides, or review connected apartment alerts. | [RentReboot](https://rentreboot.com/) · [MCP](https://rentreboot.com/.well-known/mcp/server-card.json) · [Rent data](https://rentreboot.com/average) |

## Install

```sh
npx skills add imiraoui/saas-agent-skills --skill '*'
```

To install only one skill, replace `'*'` with `pennyocr`, `ottoquest`, `winelabs`, or `rentreboot`. Read the skill and follow its connection instructions. Installation does not create a product account or transmit documents or searches. Product features, account access, and billing follow each service's terms.

The instructions are released under [MIT-0](LICENSE).
