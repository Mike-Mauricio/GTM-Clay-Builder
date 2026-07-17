---
title: Clay HTTP API
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: [[best-practices-getting-started]]
tags: [api, developer, integration]
---

# Clay HTTP API

Clay's built-in HTTP API action lets you send or retrieve data from any tool or database using an API endpoint — even when Clay doesn't offer a native integration. Supports GET, POST, PUT, and DELETE methods. This is the primary way to connect Clay to non-native services.

Two modes: **enrichment mode** (add data to existing rows) and **source mode** (import data to create new tables).

## Two Modes: Enrichment vs Source

| | Enrichment Mode | Source Mode |
|---|---|---|
| **Purpose** | Add API data to existing rows | Import data to create a new table |
| **Use when** | You already have records in Clay | You need to pull a list from an external API |
| **Processing** | Row by row | Full dataset import |
| **Pagination** | N/A | Up to 50,000 rows |
| **Account required** | Optional | Required |

**Rule of thumb:** Already have a list in Clay? Use enrichment. Need to pull a list in? Use source.

## Workspace-Level Credential Storage

Instead of entering API keys manually in the Headers field each time, save auth credentials in an **HTTP API (Headers) account**. Clay encrypts and stores the headers at the workspace level — reusable across any HTTP API enrichment column.

### Setup

1. Open your Clay table, click `Add enrichment`, select `HTTP API`
2. In the enrichment panel, click `Select header account` dropdown
3. Click `+ Add account`
4. Add auth credentials as key-value pairs:
   - `Authorization` : `Bearer YOUR_TOKEN`
   - `X-API-KEY` : `YOUR_API_KEY`
5. Name the account (e.g., `Stripe API Key`) and click `Save`

**Key points:**
- Connecting an account is optional — not every API requires auth
- Credentials entered manually in the Headers field are **visible in plain text** to anyone with table access. Use a saved account instead.
- Editing a saved account affects **every HTTP API enrichment column** across your workspace that uses it
- Manage accounts at `Settings` > `Connections`

## Enrichment Mode Setup

### Prerequisites

Gather from your API documentation:
- HTTP method (GET, POST, PUT, DELETE)
- Endpoint URL
- Authentication details (API key, bearer token)
- Parameters (headers, query params, body)

**Pro tip:** Always have the API docs open before configuring. Search "{Platform_name} API Documentation".

### Configuration Steps

**Step 1: HTTP Method**
- `GET` — Retrieve data (pull customer data, fetch user lists)
- `POST` — Create data (create leads, new contacts)
- `PUT` — Update data (modify contact info, update records)
- `DELETE` — Remove data (delete outdated records)

**Step 2: Endpoint URL** — Enter the complete URL.

**Step 3: Query String Parameters** — Key-value pairs appended after `?` in the URL. Use `/Column Name` syntax to reference Clay columns dynamically.

**Step 4: JSON Body** (POST and PUT only)

Critical JSON formatting rules:

```json
{
  "firstName": "/First Name Column",
  "lastName": "/Last Name Column",
  "email": "/Email Column",
  "score": /Score Column,
  "subscribed": true
}
```

| Value Type | Needs Quotes? | Example |
|-----------|--------------|---------|
| Strings | Yes | `"name": "Sam"` |
| Numbers | No | `"age": 30` |
| Booleans | No | `"active": true` |
| Dynamic string refs | Yes | `"email": "/Email Column"` |
| Dynamic number refs | No | `"count": /Score Column` |
| Numbers with leading zeros | Yes | `"code": "0004"` |

Common mistakes:
- `{"name": /Name Column}` -- missing quotes around string column ref
- `{"name": "John" "age": 30}` -- missing comma between fields

**Step 5: Field Paths to Return** — Specify which parts of the API response to extract. Use dot-notation (e.g., `data.user.email`). Reduces noise, speeds processing.

**Step 6: Rate Limiting** — Control requests per time window. Check your API docs for limits.

Example: `Request limit: 10` / `Duration: 1000 ms` = 10 requests per second.

**Step 7: Remove Empty Fields** — Toggle ON to exclude empty/null/undefined fields. Prevents overwriting existing data with blanks and avoids API errors from null values.

### Advanced Options

- **Integration templates** — Pre-configured setups for common APIs. Click `Browse templates` at the top of the integration window. Faster setup, fewer errors, and useful as a learning tool.
- **[[conditional-runs|Conditional runs]]** — Set formulas to only execute HTTP API when required data is present. Prevents wasted credits and error noise.
- **AI-assisted setup** — Use the `Generate` tab for AI-assisted configuration, or the `Configure` tab for manual control.

## Source Mode Setup

Import data from any HTTP API to create a new Clay table. Supports automatic pagination up to **50,000 rows**.

### Setup Steps

1. Click `Actions` > `View all sources` > `Import data from an HTTP API`
2. Select or create an account (required for sources — securely stores API credentials)
3. Configure request: method, endpoint, query params, headers, body
4. **Specify results path** — Tell Clay where the data array lives in the response (e.g., `items` if the API returns `{"items": [...], "total": 10}`). Most APIs nest data within a specific field.
5. Configure optional settings (static IP, empty value removal, redirects, timeout, retry, pagination)
6. Preview response, map fields to columns, import

### Pagination Settings

Pagination is **OFF by default** (single page fetch). Enable one of three modes:

#### Mode 1: Update Query Parameter(s)

For APIs that paginate via URL query parameters. Use these tokens as values:

| Token | Behavior | Example |
|-------|----------|---------|
| `$page` | Page number starting at 1 | `?page=1, 2, 3...` |
| `$pageZeroIndex` | Page number starting at 0 | `?page=0, 1, 2...` |
| `$offset` | Total records fetched so far | `?_start=0, 100, 200...` |
| Dot-path (e.g., `meta.next_cursor`) | Cursor value from API response | API-dependent |

#### Mode 2: Update Body Parameter(s)

For POST/PUT requests where pagination parameters go in the request body. Same tokens as above; key is a dot-path into the body (e.g., `pagination.cursor`).

#### Mode 3: Response Contains Next URL

For APIs that return a complete URL for the next page in the response. Enter the dot-path to that field (e.g., `links.next`). Clay follows it directly.

### When Clay Stops Paginating

- Page returns empty results
- A configured stop path becomes falsy (e.g., `has_more`, `data.hasNextPage`)
- Max pages path is reached (e.g., `pagination.totalPages`)
- Cursor runs out or next request would be identical (loop protection)
- **50,000 row cap** is reached

## JWT Authentication Variant

For APIs that issue **short-lived JWT tokens** (common in enterprise APIs like Gong, Snov.io), use the `HTTP API with JWT Authentication` action instead of standard HTTP API.

### How JWT Auth Works

1. **Token fetch** — Clay calls your API's token endpoint (e.g., `https://api.example.com/oauth/token`) using stored username/password credentials
2. **Authenticated request** — Clay attaches the JWT as a header (`Authorization: Bearer <token>`) on every API call
3. **Auto-refresh** — Token refreshes automatically every ~55 minutes

### When to Use JWT vs Standard

| | Standard HTTP API | HTTP API with JWT |
|---|---|---|
| **Auth flow** | Direct — static headers on every request | Two-step — token fetch, then API call |
| **Account required** | Optional | Required |
| **Account stores** | Header key-value pairs (API keys, permanent tokens) | Username, password, token endpoint URL |
| **Token expiry** | N/A | Auto-refreshed every ~55 min |

### JWT Account Setup

1. Navigate to `Settings` > `Connections`
2. Search for `HTTP API JWT Auth`, click `+ Add account`
3. Enter:
   - `Username` — API username or client ID
   - `Password` — API password or client secret
   - `JWT Token Endpoint` — URL Clay calls to obtain the JWT
4. Name the account (e.g., `Gong JWT`) and save

### JWT-Specific Configuration

When adding the enrichment, configure these fields:

- **Location of JWT token in auth response** (required) — Dot-notation path to the JWT in the token endpoint's JSON response (e.g., `access_token`, `data.token`)
- **Token type** (optional) — Prefix before the token in the auth header. Defaults to `Bearer`.
- **Auth header name** (optional) — Header name. Defaults to `Authorization`. Change only for non-standard APIs (e.g., `X-Auth-Token`).

**Important:** Each API requires its own JWT account (different token endpoints and credentials), but one account can be reused across multiple enrichment columns within the workspace.

## Best Practices

1. **Always review API docs first.** Have them open while configuring — they contain methods, endpoints, auth, and response formats.
2. **Use templates first.** Browse HTTP API templates for pre-configured setups before building from scratch.
3. **Test with one row.** Run on a single row before applying to the full table. Catches errors early and saves credits.
4. **Never hardcode API keys.** Use Clay's saved accounts for secure credential storage.
5. **Configure rate limits.** Match what the API docs specify (e.g., `Request limit: 100` / `Duration: 60000 ms` for 100 requests/minute).
6. **Use field paths.** For large API responses, specify only needed fields (`data.users.email`) — faster processing, cleaner data.
7. **Use [[conditional-runs]].** Gate HTTP API calls behind data presence checks to prevent unnecessary calls, errors, and wasted credits.
8. **Watch for hidden characters.** When copying from API docs, paste into a plain text editor first to strip hidden characters that cause parsing errors.
9. **Check for multiple API keys.** Some providers (e.g., Apollo) have different API keys for different endpoints. Use the correct key for your specific endpoint.

## Limitations

- **50,000 row cap** on source mode imports
- **Results path must point to an array** in the API response
- **Enrichment responses are not instant** — processing time depends on the external API
- Manual header credentials are **visible in plain text** to table collaborators

## Troubleshooting

- **"Body parse error" (400)** — Check JSON formatting, especially quotes around dynamic string references
- **"Please fill out your auth fields"** — JWT token location path is wrong. Check against actual token endpoint response.
- **"Access denied"** — No account selected and no manual headers for an API that requires auth
- **Use Sculptor** to diagnose errors — paste error messages for suggested fixes or share API docs to verify configuration

## Related

- [[clay-api-cli]] — Clay's developer platform (Public API, CLI, Enterprise API)
- [[clay-webhooks]] — Webhook endpoints for streaming data into Clay
- [[clay-functions]] — Reusable workflows callable across tables
- [[clay-mcp]] — Conversational prospecting via MCP protocol
- [[clay-audiences]] — Persistent enrichment layer for always-on workflows
- [[conditional-runs]] — Boolean gating to control enrichment execution
