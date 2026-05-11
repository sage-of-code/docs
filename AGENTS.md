# LiquidLogos Documentation

LiquidLogos is a UI-first perpetual DEX frontend built for professional traders. This documentation provides guides for traders, liquidity providers, and developers.

## About This Documentation

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links
- Screenshots are stored in `/images/` and captured from [liquidlogos.app](https://liquidlogos.app)

## Product Terminology

Use this terminology consistently across documentation:

- **Perpetual** or **perpetual contract** — Synthetic futures without expiration
- **Trader** — User opening positions
- **Liquidity Provider (LP)** — User providing capital to the Vault
- **Collateral** — Capital locked in account for positions
- **Margin** — Portion of collateral allocated to a position
- **Liquidation** — Automatic position closure when margin ratio reaches 100%
- **Position NFT** — ERC-721 token representing a trading position
- **Vault** — Protocol liquidity pool for traders and LPs
- **Buffer Pool** — Vault pool for trader margin
- **Insurance Pool** — Vault pool for liquidation losses

## Style Preferences

- **Tone**: Professional but approachable; speak to traders of all experience levels
- **Voice**: Active voice, second person ("you"), direct imperatives
- **Headings**: Sentence case (not Title Case)
- **Code**: Use code blocks for commands and technical references
- **Screenshots**: Use high-quality (1920x1080) screenshots to illustrate major sections
- **Links**: Use relative links `/trading/trade-interface` format

## Documentation Structure

### Guides Tab
The main guides for traders and LPs organized by user journey:

**Introduction**
- `overview.mdx` — What LiquidLogos is, core concepts
- `getting-started.mdx` — Connect wallet, first trade

**Trading**
- `trade-interface.mdx` — Professional trading terminal
- `markets.mdx` — Market discovery and filter
- `order-types.mdx` — Market, limit, stop order mechanics

**Portfolio & Positions**
- `portfolio/overview.mdx` — Collateral management, margin tracking
- `positions/overview.mdx` — Position management, liquidation protection

**Liquidity**
- `vault/overview.mdx` — LP guide, yield farming, pool risks

**Analytics**
- `analytics/overview.mdx` — Market sentiment, trading metrics

**Development**
- `development.mdx` — Local setup guide
- `quickstart.mdx` — Project structure overview

## Content Guidelines

### Writing for Traders

1. **Lead with the goal** — What does the user want to accomplish?
2. **Include screenshots** — Visual reference for UI elements
3. **Explain the "why"** — Not just mechanics, but trading implications
4. **Provide examples** — Concrete scenarios and calculations
5. **Highlight risks** — Always call out liquidation and fee implications

### Writing for LPs

1. **Explain pool mechanics** — How earning works, risks involved
2. **Show examples** — ROI calculations, yield scenarios
3. **Cover risks** — Potential losses, stress scenarios
4. **Include APY information** — What LPs can expect to earn

### Writing for Developers

1. **API documentation** — Endpoints, parameters, responses
2. **Code examples** — Working code snippets
3. **Architecture decisions** — Why things are designed a certain way
4. **Integration patterns** — How to build on top

## Adding Screenshots

Capture screenshots using:

```bash
screenshot -u https://liquidlogos.app/trade -d 1920x1080 -o images/trade.png
```

Where to place screenshots:

- `/images/` directory
- Name clearly: `home.png`, `trade.png`, `portfolio.png`, etc.
- Include in docs with: `![Alt Text](/images/filename.png)`

Key pages to screenshot:

- Home page (`/`)
- Trade terminal (`/trade`)
- Markets (`/markets`)
- Portfolio (`/portfolio`)
- Positions (`/positions`)
- Vault (`/vault`)
- Analytics (`/analytics`)

## Content Boundaries

**Document:**
- ✅ How to use the UI
- ✅ Trading concepts and strategies
- ✅ Risk management
- ✅ LP mechanics and yields
- ✅ Getting started guides

**Don't document:**
- ❌ Smart contract implementation details
- ❌ Internal architecture or backend code
- ❌ Unreleased features
- ❌ Live trading signals or investment advice
- ❌ Internal admin features

## Mintlify Components

Commonly used components in documentation:

```mdx
<!-- Card with link -->
<Card
  title="Getting Started"
  icon="rocket"
  href="/introduction/getting-started"
>
  Description of what's in that section.
</Card>

<!-- Columns layout -->
<Columns cols={2}>
  <Card title="First" icon="star" href="/path">Content</Card>
  <Card title="Second" icon="star" href="/path">Content</Card>
</Columns>

<!-- Tips and warnings -->
<Note>
  This is general information.
</Note>

<Warning>
  This is a critical warning.
</Warning>

<Tip>
  This is helpful advice.
</Tip>

<!-- Tabs -->
<Tabs>
  <Tab title="Tab 1">Content 1</Tab>
  <Tab title="Tab 2">Content 2</Tab>
</Tabs>

<!-- Tables -->
| Heading 1 | Heading 2 |
| :--- | :--- |
| Cell 1 | Cell 2 |
```

## Local Development

### Install Dependencies

```bash
npm install -g mint
```

### Preview Locally

```bash
mint dev
```

Then visit `http://localhost:3000`

### Check for Broken Links

```bash
mint broken-links
```

### Check Formatting

```bash
npm run lint
```

## Publishing Changes

1. Make changes to MDX files
2. Test locally with `mint dev`
3. Commit to the repository
4. Push to main branch
5. Changes deploy automatically to production

## File Organization

```
logos-docs/
├── index.mdx                    # Home page
├── introduction/                # Getting started guides
│   ├── overview.mdx
│   └── getting-started.mdx
├── trading/                     # Trading guides
│   ├── trade-interface.mdx
│   ├── markets.mdx
│   └── order-types.mdx
├── portfolio/                   # Portfolio management
│   └── overview.mdx
├── positions/                   # Position management
│   └── overview.mdx
├── vault/                       # LP guides
│   └── overview.mdx
├── analytics/                   # Analytics guides
│   └── overview.mdx
├── images/                      # Screenshots
├── docs.json                    # Navigation config
├── AGENTS.md                    # This file
└── CONTRIBUTING.md              # Contribution guide
```

## Quality Checklist

Before submitting documentation:

- [ ] Links all work correctly (test with `mint broken-links`)
- [ ] Screenshots are high quality (1920x1080)
- [ ] Examples include real values where possible
- [ ] Risk warnings are clear
- [ ] Tone matches existing documentation
- [ ] Formatting follows Mintlify conventions
- [ ] MDX preview looks correct locally
- [ ] No spelling or grammar errors
- [ ] Related links point to other relevant sections
- [ ] Technical accuracy verified
