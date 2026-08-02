# Bit.Bio — Design Conventions

## Naming
- Components: PascalCase (`HeroSection`, `DataCard`, `NavBar`)
- Files: kebab-case (`hero-section.html`, `data-card.css`)
- Token references: always from `design-tokens.json`, never hardcode hex values
- Images: descriptive kebab-case in `public/images/` (`hero-background.png`, `molecule-diagram.svg`)

## Component rules
- Every component in `src/components/` has a matching `.html` + `.css` file
- No inline styles — all values come from CSS custom properties mapped from tokens
- Mobile-first: base styles are mobile, use `min-width` for larger breakpoints

## Figma ↔ Code sync
- Figma component names must match `src/components/` folder names exactly
- When a token changes in `design-tokens.json`, update Figma variables in the same session
- Variants follow the pattern: `Property=Value, State=Default`

## Git
- `CLAUDE.local.md` is gitignored — never commit it
- Commit message format: `[scope] short description` (e.g. `[tokens] add semantic error color`)
