# Preflight for Cursor

Preview HTML email in supported email apps and light or dark modes. Preflight
returns a browser gallery with live progress. When Cursor displays the MCP App,
the same run also opens a compact results panel. Use `/preflight-rendering` or
ask Cursor to render your email.

## Install and connect

The plugin includes Preflight's public Cursor OAuth client ID. Your Preflight
organisation admin approves the connection in the browser. No API key or
environment variable is needed.

1. Clone this repository into `~/.cursor/plugins/local/preflight` (or install it
   from your team's Cursor marketplace, if distributed there). Reload Cursor,
   then open **Customize** and check that the Preflight MCP server and
   `preflight-rendering` skill are available. Local installs require [local
   plugin imports](https://cursor.com/docs/plugins#test-plugins-locally).
2. In **Customize → MCPs**, connect to Preflight and select the organisation to
   authorise. Ask “Which email clients and modes can I test?” to check the
   connection without spending credits.

Each requested client and mode costs one credit when Preflight accepts the
render. Checking limits, status, and existing screenshots is free. The plugin
accepts inline HTML or HTML read from a local workspace file. It does not send
email or run HTML checks.

## Smoke test

Use a synthetic email and an organisation with test credits.

- Ask for the client catalogue and remaining credits. Both queries should
  succeed without a charge.
- Ask to render synthetic HTML from a local file in two supported clients in
  the same mode. Check that the gallery link appears while captures are queued
  and that the reported charge is two credits. Where the MCP App appears, check
  that the panel updates and its Refresh action only reads results.
- Ask for status using the same test ID. Check that the result opens
  in the gallery and the balance does not change.
- Ask to compare existing captures. Check that Cursor reports only images it can
  inspect and does not start another run. A hosted URL or unsupported client
  must never trigger a paid render.
