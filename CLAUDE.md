# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A self-contained, single-file HTML onboarding form for MarginTek that collects a username and password and emails the submission to `jason@margintek.com` via Formspree.

## Architecture

Everything lives in one file: `account-setup-form.html`. There is no build step, no dependencies, and no server — it is a static HTML file that can be opened directly in a browser or hosted on any static host.

**Key implementation details:**
- **Form submission** — handled client-side via `fetch()` to `https://formspree.io/jason@margintek.com`. Formspree receives the POST and forwards it by email.
- **Logo** — the MarginTek logo is embedded as a base64 PNG data URI directly in the HTML so the file is fully self-contained (no external image file needed). Source PNG is at `C:\Data\MarginTek\Logos & Marketing\Final (13) (2)\Transparent\MarginTek-01.png`.
- **Styling** — plain CSS, no frameworks or CDN dependencies.
- **Password toggle** — show/hide eye icon is pure vanilla JS, no libraries.

## Deployment

The form is hosted on Netlify via drag-and-drop:
1. Edit `account-setup-form.html`
2. Drag the updated file onto [app.netlify.com/drop](https://app.netlify.com/drop) to redeploy

## Formspree

Submissions route to `https://formspree.io/jason@margintek.com`. If the endpoint needs to change (e.g. switching to a named form ID), update the URL in the `fetch()` call inside the `<script>` block at the bottom of the file.

## Git & GitHub

Remote: `https://github.com/GannipGannop/onboarding-form.git`  
Branch: `master`
