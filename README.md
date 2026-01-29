# Daysift Landing Page

Marketing website for Daysift - a Chrome extension for instant access to your work history.

## Files

| File | Description |
|------|-------------|
| `index.html` | Main landing page (version A) |
| `index-b.html` | Variant landing page (version B) - bolder typography, marquee, hover effects |
| `privacy.html` | Privacy policy |
| `terms.html` | Terms of service |
| `logo.png` | Current logo asset |
| `DEMO_SPEC.md` | Spec for the interactive demo carousel |

## Brand

**Colors:**
- Background: `#FAFAF9`
- Foreground: `#1C1917`
- Muted: `#78716C`
- Accent (orange): `#F46B45`
- Border: `#E7E5E4`

**Font:** Inter (Google Fonts)

## Demo Carousel

The landing page features an interactive demo showing 5 screens:
1. **Search** - Typing "Q3 budget", showing results with favicons
2. **Filters** - Filter pills narrowing results to Google Docs
3. **AI Search** - Question with AI answer and code blocks
4. **Notes** - `/notes` command with floating notes window
5. **Commands** - Slash commands list (`/doc`, `/sheet`, `/figma`, etc.)

Auto-advances every 5 seconds with progress bar indicator. Manual switching pauses autoplay.

## Current Pricing (Free Tier)

- 14 days of history search
- 5 pinned items
- 5 notes
- 30 AI credits/month

## Deployment

TODO: Connect to Vercel/Netlify for auto-deploy

## Local Preview

```bash
open index.html
# or
open index-b.html
```
