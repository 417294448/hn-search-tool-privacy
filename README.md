# HN Multi-Language Search Assistant Privacy Policy

Last updated: 2026-10-04

## Overview

HN Multi-Language Search Assistant is a browser extension that lets you search Hacker News in your own language. It generates English search queries, translates titles and comments using the browser's built-in on-device translation, and can rewrite your comments into natural English using a large language model (LLM) endpoint that you configure yourself. This privacy policy explains how we handle your data.

## Data Collection

HN Multi-Language Search Assistant does **not** collect, transmit, or store any personal information on servers operated by the developer. There is no developer-operated backend, account system, or cloud database, and the extension contains no analytics, tracking, advertising, or telemetry code. All data is processed and stored locally on your device, with one exception: text you choose to send to **your own configured LLM endpoint** (see below).

## Local Storage

- **Settings**: Your configuration (LLM base URL, API key, model name, target language, sort/date/type preferences, translation toggles, and output color) is stored locally using `chrome.storage.local`. It is **not** synced to the cloud.
- **Search History**: Up to the 20 most recent search entries (your original query, the generated English query, and a timestamp) are stored locally on your device.
- **API Key**: Your API key is stored in plain text in local extension storage only. It is never synced to the cloud and is never sent to any service other than the endpoint you configured.
- **Page Content**: Titles, post bodies, and comments are translated by the browser's **built-in on-device translation** (Chrome 138+ / Edge 143+). This text is processed locally and does not leave your device.

## Data Usage

The extension uses your data only to provide its core functionality:

- Reading your settings to configure search and translation.
- Reading on-page titles, post bodies, and comments (only on `hn.algolia.com` and `news.ycombinator.com`) to display translations.
- Using your local search history to let you repeat recent searches.
- Sending only the necessary text to the **endpoint you configure yourself** (an OpenAI-compatible chat completions API) when you actively use an LLM-powered feature:
  - **Generate search query**: the native-language query you type.
  - **Test connection**: the fixed string `Hello world`.
  - **Write an English comment**: the comment you write, plus the related post title and the comment being replied to (each truncated to about 600 characters for context).

No browsing history, identity information, or unrelated data is ever sent.

## Third-Party Disclosure

HN Multi-Language Search Assistant does not share any data with third parties. All processing happens locally on your device, except when you actively use an LLM-powered feature, in which case the relevant text is sent to the LLM endpoint **you configured** (for example OpenAI, DeepSeek, Kimi, Qwen, or a local Ollama instance). How that provider collects, stores, and processes your data is governed by **its** privacy policy, which the developer of this extension does not control. The extension includes no analytics SDKs, ad networks, or social plugins.

## Permissions

HN Multi-Language Search Assistant requests the following permissions:

- `storage` - To save your settings and search history locally
- `scripting` - To inject the translation and comment-assist interface into the target pages
- `*://hn.algolia.com/*` - To read and translate titles, post bodies, and comments, and to inject the comment-assist UI on the Hacker News search results page
- `*://news.ycombinator.com/*` - To read and translate titles, post bodies, and comments, and to inject the comment-assist UI on Hacker News detail and list pages
- `*://*/*` (optional) - Requested at runtime, only after an explicit user action, to reach the LLM endpoint you configure yourself

These permissions are used solely for the core functionality of the extension.

## Changes to This Policy

We may update this privacy policy from time to time. Any changes will be reflected in this document, along with an updated "Last updated" date.

## Contact

If you have any questions about this privacy policy, please contact us through the extension's GitHub repository.
