---
title: "HTTP API - Clay Docs"
source: "https://university.clay.com/docs/http-api-integration-overview"
author:
published:
created: 2026-07-14
description: "Facilitate seamless integration and connectivity with any APIs."
tags:
  - "clippings"
---
Overview

HTTP API lets you send or retrieve data from any tool or database using an API endpoint, even when Clay doesn't offer a native integration. With it, you can pull external data into your Clay table or push data out from Clay using any endpoint and method (GET, POST, PUT, DELETE).

### Common use cases

- Pull customer data from your CRM.
- Create leads in your marketing platform.
- Update contact information in your database.
- Access public datasets (NYC Open Data, government APIs).
- Connect to custom tools without native Clay integrations.

## Choose your path

Before you begin, decide which approach fits your needs.

### HTTP API enrichment (most common)

Use this when you want to add API data to existing rows in your Clay table.

- Process data row by row.
- Add information to existing records.
- Works with any API endpoint.

Jump to enrichment setup (see below).

### HTTP API as source

Use this when you want to import data from an API to create a new table.

- Import datasets from external APIs.
- Build lists from third-party services.
- Start workflows with external data.
- Supports pagination (up to 50,000 rows).
- Multiple pagination methods: page-based, offset, cursor, and full URL.

Jump to source setup (see below).

### Not sure which to choose?

- Already have a list of companies, people, or records in Clay? → Use enrichment.
- Need to pull a list from an external API? → Use as source.

## Storing authentication credentials at the workspace level

Instead of entering API keys or bearer tokens manually in the `Headers` field each time, you can save your auth credentials in an `HTTP API (Headers) account`. Clay encrypts and stores the headers at the workspace level, making them reusable across any HTTP API enrichment column.

Setting up an HTTP API (Headers) account from the enrichment panel:

1. Open your Clay table and click `Add enrichment`.
2. Search for and select `HTTP API`.
3. In the enrichment panel, click the `Select header account` dropdown.
4. Click `+ Add account`.
5. Under `API Request Headers`, add your auth credentials as key-value pairs — for example:
	- Key: `Authorization` | Value: `Bearer YOUR_TOKEN`
		- Key: `X-API-KEY` | Value: `YOUR_API_KEY`
6. Name the account (e.g., `Stripe API Key`) and click `Save`.

The saved account will now appear in the `Select header account` dropdown. Select it to apply the headers to this enrichment.

**Note:** You can also manage existing accounts at any time from `Settings → Connections`. Keep in mind that editing a saved account will affect every HTTP API enrichment column across your workspace that uses it.

A few things to know:

- **Connecting an account is optional.** Not every API requires auth headers. If no account is selected, the enrichment will still run — as long as the API endpoint doesn't require authentication.
- **The Headers field includes a reminder.** When configuring the `Headers` field manually, Clay surfaces a tip directing you to use the HTTP API app account for secure credentials instead.
- **Credentials entered manually in the Headers field** are visible in plain text to anyone with access to the table column. Use a saved account to avoid exposing keys.
- **APIs that require auth** will return an error (e.g., `access denied`) if no account is selected and no headers are passed manually.

If you're connecting to an API that uses JWT authentication (dynamically issued tokens), use the `HTTP API with JWT Authentication` action instead, which uses a separate account type that stores your token endpoint URL and credentials. See the HTTP API with JWT Authentication guide for details.

## HTTP API enrichment

### Prerequisites

Before configuring HTTP API, gather these details from your API documentation:

- **HTTP method:** GET, POST, PUT, or DELETE.
- **Endpoint URL:** The specific API endpoint address.
- **Authentication:** API key, bearer token, or other credentials.
- **Parameters:** Headers, query parameters, or body content as specified by the API.

Pro tip: Always have the API documentation open before setting up HTTP API. Search for "{Platform\_name} API Documentation" online (e.g., "Gong API Documentation").

### Setup method: choose your approach

When you add HTTP API to your table, you'll see two tabs: `Generate` (AI-assisted) and `Configure` (manual). Choose the method that works best for you.

## Option B: Manual configuration

Choose manual configuration if you need precise control or have complex requirements. You can also switch to the `Configure` tab at any time to adjust AI-generated settings.

### Step 1: HTTP method

Select the HTTP method based on what you want to do:

- `GET` — Retrieve data (e.g., pull customer data from your CRM, fetch a list of users).
- `POST` — Create new data (e.g., create a new lead in your marketing platform, create a new contact).
- `PUT` — Update existing data (e.g., update contact information in your database, modify user information).
- `DELETE` — Remove data (e.g., remove outdated records, delete a record).

### Step 2: API endpoint URL

Enter the complete URL where your request will be sent.

### Step 3: Query string parameters

Add parameters to filter or refine your request. These appear in the URL after a `?` symbol.

Example:

- Key: `email` + Value: `/Email Column`
- Key: `status` + Value: `active`

### Step 4: JSON body

For POST and PUT requests, specify the data to send in the request body.

Important JSON formatting rules:

- String values need quotes: `"name": "Sam"`
- Numbers and booleans don't: `"age": 30`, `"active": true`
- Dynamic column references for strings need quotes: `"email": "/Email Column"`
- Dynamic column references for numbers don't: `"count": /Score Column`
- Exception: Numbers with trailing zeros (e.g., `0004`) need quotation marks.

Example body configuration:

{ "firstName": "/First Name Column", "lastName": "/Last Name Column", "email": "/Email Column", "score": /Score Column, "subscribed": true }

Common mistake:

`❌ Wrong: {"name": /Name Column}   ✅ Correct: {"name": "/Name Column"}      ❌ Wrong: {"name": "John" "age": 30}   ✅ Correct: {"name": "John", "age": 30}   `

### Step 6: Field paths to return

Specify which parts of the API response you want to retrieve. Use this to filter out unnecessary data.

Example API response:

```javascript
{ "data": { "user": { "id": 12345, "name": "John Doe", "email": "john@example.com" } }}
```

Field path to extract email: `data.user.email`

This returns only: `john@example.com`

Benefits: Faster processing, cleaner data, easier to work with.

### Step 7: Rate limiting

Control how many API requests you can send within a given time frame. Check your API documentation for rate limits.

Example configuration:

`Request limit: 10   Duration (ms): 1000   `

This means: 10 requests per second.

### Step 8: Remove empty fields from request

Toggle `ON` to automatically exclude empty, null, or undefined fields from your request.

Why use this:

- Prevents overwriting existing data with blank values.
- Avoids API errors from unexpected null values.
- Keeps requests clean and efficient.

## Advanced options

### Using integration templates

Click the `Browse templates` button at the top of the integration window to access pre-configured setups for common use cases.

Benefits:

- Faster setup — Configure in seconds.
- Reduced errors — Pre-tested configurations.
- Learning tool — See proper API structure.

After using a template, you can adjust any settings to match your specific needs.

### Conditional runs

Set up conditional run formulas to only execute HTTP API when required data is present. This prevents unnecessary API calls, error messages, and wasted credits.

Example: Only run if email column is not empty.

### Testing and validation

Before running on your entire table:

- Test with a single row.
- Verify the configuration works.
- Check the response data.
- Then run on full table.

Why: Saves credits and catches errors early.

## HTTP API as source

HTTP API as source allows you to import data directly from any HTTP API into Clay tables as a starting point for list building.

### When to use this

Use HTTP API as source when you want to:

- Build lists from external APIs.
- Import datasets from third-party services.
- Create tables from endpoints returning multiple records.
- Start workflows with data from external sources.

Example use cases:

- Pulling trip hazards from NYC Open Data API
- Importing event listings or class schedules
- Fetching product catalogs from e-commerce APIs
- Retrieving fantasy sports team data
- Accessing government or public datasets

### Setup steps

**Step 1: Start import**

1. Click `Actions` → `View all sources`.
2. Search for `Import data from an HTTP API`.
3. Select it.

**Step 2: Configure account (required)**

Select or create an account that contains your API authentication. Accounts are mandatory for sources because they securely store sensitive information like API keys and authorization tokens.

**Step 3: Configure request**

Configure your request settings:

- **Method:** Select HTTP method (typically GET for imports).
- **Endpoint:** Enter the API endpoint URL.
- **Query parameters:** Add key-value pairs for filtering data.
- **Headers:** Add authentication and other required headers.
- **Body:** Add request body if needed (for POST/PUT methods).

**Step 4: Specify results path**

This is a critical step unique to sources. Tell Clay exactly where in the API response your data array is located.

Example: If your API returns:

```javascript
{ "items": [...], "total": 10}
```

You'd specify `items` as the results path. Most APIs nest their data within a specific field rather than returning an array at the root level.

**Step 5: Configure optional settings**

- **Use static IP:** Enable for allow-listing requirements.
- **Remove empty values:** Exclude null or empty fields.
- **Follow redirects:** Set max redirects if needed.
- **Response timeout:** Specify timeout in milliseconds.
- **Retry on failure:** Configure retry attempts and conditions.
- **Pagination:** Configure automatic pagination (see Pagination settings below).

**Step 6: Preview and import**

1. Preview the API response to verify the data structure.
2. Map the API response fields to table columns.
3. Import the data to create your new table.

### Pagination settings

HTTP API as source supports automatic pagination up to 50,000 rows. Pagination is configured in Step 5 under the `Pagination` dropdown — it's set to `Off` by default, which means Clay fetches a single page exactly as before.

**To enable pagination, select one of three modes:**

**`Update query parameter(s)`** — Use when your API advances pages via URL query parameters. After selecting this mode, enter the query parameter name(s) as the key and one of the following as the value:

- `$page` — page number starting at 1 (e.g., `?page=1, 2, 3…`)
- `$pageZeroIndex` — page number starting at 0 (e.g., `?page=0, 1, 2…`)
- `$offset` — total records fetched so far (e.g., `?_start=0, 100, 200…`)
- A dot-path into the API response to use a cursor value returned by the API (e.g., `meta.next_cursor`)

**`Update body parameter(s)`** — Use for POST/PUT requests where pagination parameters go in the request body instead of the URL. Same token and dot-path options as above; the key is a dot-path into the request body (e.g., `pagination.cursor`).

**`Response contains next URL`** — Use when the API returns a complete URL for the next page in the response body. Enter the dot-path to that field (e.g., `links.next`). Clay follows it directly without re-applying your base query parameters.

**When Clay stops paginating:**

- The page returns empty results.
- A stop path you configure becomes falsy (e.g., `has_more`, `data.hasNextPage`).
- A max pages path you configure is reached (e.g., `pagination.totalPages`).
- The cursor runs out or the next request would be identical to the previous one (loop protection).
- The 50,000 row cap is reached.

**Note:** Always check your API documentation for the correct pagination format and parameter names. Using incorrect pagination settings may result in duplicate or missing data.

### Limitations

Important considerations:

- **Array output required:** Make sure the results path points to an array in the API response.
- **Pagination limit:** Sources support up to 50,000 rows. If your API returns more than 50,000 records, only the first 50,000 will be imported.
- **Results path matters:** Take time to examine your API response structure. Some APIs nest data several levels deep (e.g., `data.results.items`).
- **Account security:** Your API credentials are stored securely and won't be exposed in the table configuration.

## Best practices

### Start with documentation

Always review the API documentation before configuration. It contains everything you need: methods, endpoints, authentication, headers, parameters, and response formats.

### Use templates first

Browse HTTP API templates for pre-configured setups. Templates save time and reduce configuration errors.

### Test with one row

Before running on your entire table:

1. Test with a single row.
2. Verify the configuration works.
3. Check the response data.
4. Then run on full table.

Why: Saves credits and catches errors early.

### Secure authentication

- Never hardcode API keys in requests.
- Use Clay's built-in authentication features.
- Store credentials securely.

### Configure rate limits

If the API documentation specifies limits, configure them in your enrichment.

Example: 100 requests per minute.

`Request limit: 100   Duration: 60000 ms   `

### Optimize with field paths

For large API responses, specify only needed fields:

`data.users.email   data.users.name   `

Benefits: Faster processing, cleaner data, easier to work with.

### Use conditional runs

Set up conditional run formulas to only execute HTTP API when required data is present.

This prevents:

- Unnecessary API calls
- Error messages
- Wasted credits

### Document complex setups

For complex HTTP API configurations:

- Add notes about what each setting does.
- Document field mappings.
- Include example responses.

Benefits:

- Makes troubleshooting easier.
- Simplifies replication to other tables.

## Troubleshooting

### Hidden characters in API documentation

When copying from API documentation:

1. Paste into a plain text editor first.
2. Check for hidden characters.
3. Remove any found.
4. Copy clean text into Clay.

This reveals any hidden characters that might cause parsing errors.

### Multiple API keys

Some data providers (like Apollo) have different API keys for different endpoints. Make sure you're using the correct key for your specific endpoint.

### Using AI to diagnose issues

If you encounter errors, use Sculptor to help:

- Paste error messages for suggested fixes.
- Share API docs to verify configuration.
- Get help interpreting unexpected responses.

## FAQs

### Why do I need quotation marks around dynamic string variables?

As of October 2024, you must enclose dynamic string variables in quotation marks when using the HTTP API enrichment column. This ensures proper JSON formatting.

Example:

`✅ Correct: {"email": "/Email Column"}   ❌ Wrong: {"email": /Email Column}   `

### What if a data provider has multiple API keys?

Some data providers have multiple API keys for different APIs. For example, Apollo has several APIs you can create keys for. Make sure you're using the correct API key for the specific endpoint you're calling.

### How do I handle hidden characters in API documentation?

When copying from API documentation, paste your code into a plain text editor first. This reveals any hidden characters that might cause parsing errors. Remove them before pasting into Clay.

### When should I use HTTP API as source vs. enrichment?

- Use **enrichment** if you already have a list of records in Clay and want to add API data to them.
- Use **as source** if you need to pull a list from an external API to create a new table.

### How does pagination work with HTTP API as source?

HTTP API as source supports automatic pagination up to 50,000 rows. Pagination is off by default. When enabled, Clay handles fetching subsequent pages automatically based on your configuration, stopping when the API returns no more data, your stop condition is met, or you reach 50,000 total rows.

You can configure three pagination modes depending on how your API works: updating a query parameter (page-based, offset, or cursor), updating a body parameter (for POST/PUT requests), or following a next URL returned in the response.

Table of contents[Common use cases](#common-use-cases)

[

Choose your path

](#choose-your-path)[HTTP API enrichment (most common)](#http-api-enrichment-most-common)[HTTP API as source](#http-api-as-source-2)[Not sure which to choose?](#not-sure-which-to-choose)[Storing authentication credentials at the workspace level](#storing-authentication-credentials-at-the-workspace-level)

[

HTTP API enrichment

](#http-api-enrichment)[Prerequisites](#prerequisites)[Setup method: choose your approach](#setup-method-choose-your-approach)[When to use AI-assisted setup](#when-to-use-ai-assisted-setup)[How it works](#how-it-works)[Troubleshooting with AI](#troubleshooting-with-ai)[Tips for best results](#tips-for-best-results)

[

Option B: Manual configuration

](#option-b-manual-configuration)[Step 1: HTTP method](#step-1-http-method)[Step 2: API endpoint URL](#step-2-api-endpoint-url)[Step 3: Query string parameters](#step-3-query-string-parameters)[Step 4: JSON body](#step-4-json-body)[Step 6: Field paths to return](#step-6-field-paths-to-return)[Step 7: Rate limiting](#step-7-rate-limiting)[Step 8: Remove empty fields from request](#step-8-remove-empty-fields-from-request)

[

Advanced options

](#advanced-options)[Using integration templates](#using-integration-templates)[Conditional runs](#conditional-runs)[Testing and validation](#testing-and-validation)

[

HTTP API as source

](#http-api-as-source)[When to use this](#when-to-use-this)[Setup steps](#setup-steps)[Pagination settings](#pagination-settings)[Limitations](#limitations)

[

Best practices

](#best-practices)[Start with documentation](#start-with-documentation)[Use templates first](#use-templates-first)[Test with one row](#test-with-one-row)[Secure authentication](#secure-authentication)[Configure rate limits](#configure-rate-limits)[Optimize with field paths](#optimize-with-field-paths)[Use conditional runs](#use-conditional-runs)[Document complex setups](#document-complex-setups)

[

Troubleshooting

](#troubleshooting)["Body parse error" (400 error)](#body-parse-error-400-error)[Hidden characters in API documentation](#hidden-characters-in-api-documentation)[Multiple API keys](#multiple-api-keys)[Using AI to diagnose issues](#using-ai-to-diagnose-issues)[Error codes reference](#error-codes-reference)

[

FAQs

](#faqs)[Why do I need quotation marks around dynamic string variables?](#why-do-i-need-quotation-marks-around-dynamic-string-variables)[What if a data provider has multiple API keys?](#what-if-a-data-provider-has-multiple-api-keys)[How do I handle hidden characters in API documentation?](#how-do-i-handle-hidden-characters-in-api-documentation)[When should I use HTTP API as source vs. enrichment?](#when-should-i-use-http-api-as-source-vs-enrichment)[How does pagination work with HTTP API as source?](#how-does-pagination-work-with-http-api-as-source)[What happens if my API returns more than 50,000 rows?](#what-happens-if-my-api-returns-more-than-50000-rows)