# copy-to-webflow

Single-page utility that builds a Webflow-compatible clipboard payload (`@webflow/XscpData`) from editable form inputs.

## What it does
- Lets you edit a name, tagline, two status badges, and an HTML embed snippet.
- Includes an AI prompt workflow that can call OpenAI directly **or** any OpenAI-compatible endpoint (including keyless/self-hosted setups) to generate a full Webflow clipboard JSON payload.
- Generates a full Webflow node/style payload with fresh IDs on each copy.
- Copies JSON into the clipboard as `application/json` so you can paste directly in the Webflow canvas.
- Shows a short JSON preview after copy for quick sanity checking.

## Why it’s useful
This is a pragmatic approach for repeatable “template-like” inserts in Webflow without rebuilding the same structure manually each time.

## Notes
- The payload currently hardcodes a set of known Webflow style IDs, which is convenient but ties output to that style map.
- Clipboard writing relies on `document.execCommand('copy')` with a copy-event handler to set custom MIME data.
- The AI feature runs client-side in your browser. OpenAI requires your API key; custom/self-hosted OpenAI-compatible endpoints can be used without a key.
