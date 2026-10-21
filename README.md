<div align="center">

<img src="https://okeystay.com/og-en.png" alt="OkeyStay — verified holiday rentals" width="640" />

### Holiday rentals built to be read by AI

[Website](https://okeystay.com) · [MCP endpoint](https://okeystay.com/mcp) · [llms.txt](https://okeystay.com/llms.txt) · [Sitemap](https://okeystay.com/sitemap.xml) · [Legal notice](https://okeystay.com/en/legal)

</div>

---

## What is OkeyStay?

OkeyStay is an international holiday-rental discovery platform, built so that both search engines and AI assistants can read, understand and cite its listings — with server-rendered content, Schema.org structured data, a Markdown version of every listing, an [`llms.txt`](https://okeystay.com/llms.txt) index and a public **remote MCP server**.

Where a listing provides them, OkeyStay surfaces facts a traveller actually needs: the tourist-licence number, the town worked out from the listing's map coordinates, measured distances to the beach and the airport, and the **total price** for the chosen dates (cleaning included) rather than a nightly teaser. What any single listing exposes depends on that listing's own data.

## Remote MCP server

Point an MCP client at the endpoint and it can search stays, read a listing, check availability and prepare a booking.

- **Endpoint:** `https://okeystay.com/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** open — no credentials required
- **Protocol revision:** `2025-06-18`

### Tools

| Tool | Returns |
|------|---------|
| `search_stays` | Searches holiday rentals; filter by town, dates and guests. With check-in/check-out each result includes the total price of the stay (cleaning included); without dates, the lowest nightly price of the next 60 days. Called without a place, it lists the destinations that exist. |
| `get_stay` | The full listing of one stay: description, highlights, FAQ, capacity, check-in/check-out times, tourist registration number, measured distances and — with dates — the total price and availability. |
| `get_availability` | Day-by-day availability, nightly price and minimum stay for one stay, for up to 93 days. |
| `prepare_booking` | Checks a stay is free for the given dates and guests, and returns the total price (cleaning included), the cancellation policy and a direct booking link with dates and guests pre-filled. The traveller confirms and pays securely on OkeyStay. |

### Connect

Most MCP clients accept a remote server by URL:

```json
{
  "mcpServers": {
    "okeystay": {
      "url": "https://okeystay.com/mcp"
    }
  }
}
```

For a client that only speaks stdio, bridge it with [`mcp-remote`](https://www.npmjs.com/package/mcp-remote):

```bash
npx mcp-remote https://okeystay.com/mcp
```

Then ask your assistant something like *"find a holiday rental in Torremolinos for 2 guests next weekend and show the total price."*

## Links

- 🌐 Website — https://okeystay.com
- 🤖 MCP endpoint — https://okeystay.com/mcp
- 📄 llms.txt — https://okeystay.com/llms.txt
- 🗺️ Sitemap — https://okeystay.com/sitemap.xml
- ⚖️ Legal notice — https://okeystay.com/en/legal
- 💬 Contact — https://okeystay.com/en/contact
- 💼 LinkedIn — https://www.linkedin.com/in/okey-stays-15942943b/

<div align="center">
<sub>Operated by ActiveNetwork Global SL · part of the InBoxIA ecosystem.</sub>
</div>
