# Bonds Trade Design System

## Brand direction

Bonds Trade should feel credible, calm, and contemporary: a clear investment
brand rather than a generic fintech dashboard. The visual identity is anchored
by the supplied Bonds Trade wordmark: deep navy lettering with a bright blue
underline. Use navy for structure and trust, and blue as a focused accent.

The page remains Arabic-first and right-to-left. Preserve Arabic content,
natural Arabic reading order, and the IBM Plex Sans Arabic typeface. Do not
mirror inherently left-to-right data controls or charts when that would reduce
their usability.

## Design principles

- **Clarity before decoration:** make investment information and next steps easy
  to scan.
- **Measured confidence:** use restrained color, consistent surfaces, and
  typography with a clear hierarchy.
- **Arabic by default:** design and test for RTL layouts at every viewport size.
- **Accessible interaction:** provide visible keyboard focus, readable
  contrast, and respect reduced-motion preferences.
- **Consistent components:** use shared tokens and component patterns instead
  of one-off visual treatments.

## Core tokens

The current implementation defines these CSS custom properties in
`index.html`. Keep this table aligned with the source when tokens change.

| Token | Value | Use |
| --- | --- | --- |
| `--brand-navy-dark` | `#070D1E` | Deep background for footer and high-contrast elements |
| `--brand-navy` | `#0D1B3E` | Primary brand structure, headings, and executive cards |
| `--brand-navy-light` | `#162B5E` | Secondary brand surface and gradient stops |
| `--brand-blue` | `#00A6FB` | Electric cyan brand accent and interactive highlights |
| `--brand-blue-deep` | `#0582CA` | Accessible deep azure for primary emphasis, lines, and links |
| `--brand-blue-soft` | `#E8F4FD` | Soft tinted surfaces and icon containers |
| `--brand-green` | `#00C896` | Returns, profit badges, and positive cash flow metrics |
| `--brand-green-soft` | `#E6FBF5` | Background for live badges and profit metrics |
| `--brand-gold` | `#F5A623` | Risk and asset-backed highlight indicators |
| `--bg-page` | `#F6F8FC` | Off-white premium page canvas |
| `--bg-card` | `#FFFFFF` | Main card surfaces |
| `--text-heading` | `#0F172A` | Primary high-contrast text |
| `--text-body` | `#334155` | Body copy |
| `--text-muted` | `#64748B` | Secondary and supporting text |
| `--border-light` | `#E2E8F0` | Dividers, card borders, and control outlines |
| `--radius-sm` | `8px` | Buttons, controls, and form inputs |
| `--radius-md` | `14px` | Standard cards and feature boxes |
| `--radius-lg` | `22px` | Major hero cards, split containers, and calculator frame |

### Typography and spacing

- Font family: `IBM Plex Sans Arabic`, with a sans-serif fallback.
- Body text token: `--type-body: 1rem`.
- Section headings: `--type-heading: clamp(2rem, 3.2vw, 2.75rem)`.
- Hero heading: `--type-display: clamp(2.4rem, 4.5vw, 3.6rem)`.
- Section spacing: `--space-section: clamp(4rem, 7vw, 6.5rem)`.
- Standard card padding: `--space-card: 2rem`.
- Use generous line-height for Arabic paragraphs and avoid overly long text
  measure.

## Component guidance

- **Header:** white, subtly elevated, fixed, and visually quiet; use the local
  wordmark and a prominent navy action.
- **Primary action:** navy background, white text, rounded control corners, and
  a blue hover state. Preserve a clear focus outline.
- **Cards:** white surface, consistent rounded corners and border, restrained
  shadow, and only subtle hover lift where the card is interactive.
- **Icons:** use a consistent blue-on-pale-blue treatment; decorative icons
  should not compete with Arabic headings.
- **Forms:** keep labels visible, controls high contrast, and keyboard focus
  obvious. Keep sliders left-to-right where that matches their conventional
  value progression.
- **Charts and financial figures:** label axes and units clearly, use the brand
  blue for the data series, and retain sufficient contrast. Pair actual
  performance charts with a dated data table and state whether dividends are
  included.
- **Footer:** deep navy foundation with white headings and muted light text.

## Brand assets

- Wordmark: `bonds-trade-english-black.png`
- Favicon: `bonds-trade-favicon-white-background.png`

Use local assets rather than remote image hosts. On the dark footer, the current
wordmark may use a white filter so it remains legible.

## Responsive and accessibility requirements

- Preserve the RTL document direction at all breakpoints.
- Collapse multi-column content to a single column on narrow screens.
- Avoid horizontal overflow at mobile widths.
- Use `:focus-visible` styles for interactive elements.
- Honor `prefers-reduced-motion`.
- Keep meaningful alternative text for brand images and accessible labels for
  charts and controls. Prefer native tables alongside financial charts so exact
  values remain available to assistive technology and mobile users.

## Financial performance presentation

- Separate actual results from projections and keep their labels visually
  distinct.
- State the measurement period, currency, and data cutoff for every actual
  performance view.
- Do not describe share-value appreciation as total investor return when cash
  dividends are excluded.
- Clearly label any dividend values derived from an allocation rule rather
  than verified against payment records.
- Explain that the 50% distribution / 50% retention policy applies to realized
  profits, not to invested principal.
- Do not publish projections until their assumptions have been reconciled with
  the current distribution policy.

## Implementation note

This is a lightweight CSS-token system in the existing static page, not a
separate component library. If styles move into shared files later, preserve
the token names and keep this document synchronized with the implementation.
