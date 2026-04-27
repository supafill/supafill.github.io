---
permalink: /privacy-policy/
title: Privacy Policy
---

# SupaFill Privacy Policy

**Last updated: April 20, 2026**

## Overview

SupaFill is a browser extension that helps developers and testers fill forms with realistic fake data. We are committed to protecting your privacy and collect only the minimum data necessary to operate the features you choose to use.

## Core Functionality — No Data Collection

The core form-filling functionality of SupaFill operates entirely locally in your browser:

- We don't track your browsing history
- We don't log, store, or transmit any form data you fill
- We don't use analytics or tracking tools
- All fake data (names, emails, addresses, etc.) is generated locally using built-in algorithms with no external API calls

### Local settings storage

SupaFill stores the following **only in your browser** using the browser's `storage.sync` API:

- Locale preference
- Custom field rules
- Ignored-field patterns

These settings sync across your browsers if you're signed into your browser account (Chrome, Firefox, etc.), but are never sent to SupaFill's developers.

## Optional Feedback Feature (v1.4.0+)

SupaFill includes an **opt-in** feedback form accessible via the popup's "Feedback" link. This feature only activates when you actively choose to submit a bug report or feature request. If you never click "Feedback" and never submit the form, no data is collected or transmitted.

### What is collected when you submit feedback

When you voluntarily submit the feedback form, the following data is sent:

- **Feedback type** (bug or feature request)
- **Title and description** you wrote
- **Email address** — optional, only if you choose to provide one for follow-up
- **Extension version, operating system platform, and browser user-agent string** — only if the "Attach version + browser info" checkbox is enabled (enabled by default, but you can uncheck it before submitting)

### Where feedback data goes

Feedback submissions are sent to **Web3Forms** (https://web3forms.com), a third-party form-submission service. Web3Forms delivers the submission to the SupaFill developer's email address. Web3Forms' handling of this data is governed by their privacy policy:

- Web3Forms Privacy Policy: https://web3forms.com/privacy
- Web3Forms Terms: https://web3forms.com/terms

Feedback data is used only to improve SupaFill. It is not sold, shared with advertisers, or used for any purpose beyond triaging and responding to reports.

## Permissions Explained

SupaFill requires the following browser permissions:

- **`activeTab`**: To fill forms on the current page when you click the extension
- **`contextMenus`**: To show "Fill this form" options when you right-click
- **`storage`**: To save your settings locally
- **`<all_urls>`**: To work on any website and fill forms inside iframes

## Data Sold or Shared

SupaFill does **not**:

- Sell any user data
- Share data with advertisers or data brokers
- Use data for creditworthiness, lending, or any unrelated purpose
- Transmit form contents you fill with the extension

## Changes to This Policy

We may update this privacy policy from time to time. Any changes will be reflected in the "Last updated" date. Material changes (e.g., new data collection) will be noted in the extension's changelog.

## Contact

If you have questions about this privacy policy, please contact us through the extension's store listing support page or by using the Feedback form within the extension.

---

**SupaFill** - Fill everything in a snap.
