# LLM Instructions for PHES-EF

General instructions for AI assistants working on the PHES-EF repository.

## Project Overview

**PHES-EF** (Public Health Environmental Surveillance Evaluation Framework) is an international consensus study developing evaluation standards for wastewater-based surveillance using Quarto for website generation.

## Repository Structure

```
PHES-EF/
├── _quarto.yml           # Quarto configuration
├── *.qmd                 # Content pages (index, about, methods, etc.)
├── assets/               # Images, logos, SCSS themes, CSL files
├── data/                 # CSV data files (schema, example terms)
├── docs/                 # Build output (DO NOT EDIT - auto-generated)
├── references.bib        # Bibliography
└── README.md             # Project documentation
```

## Git & Commit Practices

- **Do not commit without explicit user approval**
- Draft commit messages as plain text (no wrapped text boxes)
- **Do not credit AI or LLMs in commit messages**
- Follow existing commit message style in the repository

## R Environment

- **Minimum R version**: R >= 4.2.0 (compatibility floor for StatsCan/ICES)
- **Package management**: Uses renv
  - Run `renv::restore()` after cloning
  - Use `renv::snapshot()` after adding packages
  - Commit `renv.lock`, `.Rprofile`, and `renv/activate.R`
  - Do NOT commit `renv/library/`, `renv/staging/`, or `renv/local/`

## Quarto Development

**Preview locally:**
```bash
quarto preview
```

**Build locally:**
```bash
quarto render
```

**Publishing:**
- Automatic via GitHub Actions on push to main
- Output goes to `docs/` directory
- Hosted on GitHub Pages

## File Guidelines

- **Never create files unless absolutely necessary**
- **Always prefer editing existing files**
- **Never proactively create documentation** unless explicitly requested
- Quarto pages should follow existing formatting conventions
- Use Vancouver citation style (defined in `assets/vancouver.csl`)

## Code Review Standards

- Review major coding plans with the user before implementation
- Ensure accessibility and EDI considerations
- Maintain consistent styling with existing pages
- Test rendering before committing

## Testing

Before committing changes:
1. Run `quarto preview` to check local rendering
2. Verify all links work
3. Check image paths are correct
4. Ensure bibliography renders properly

## Dependencies

Check DESCRIPTION file for R package dependencies. Currently includes:
- rmarkdown
- gt (for tables)

## Contributing

This is an open science project (CC-BY-SA-4.0 license). All contributions should:
- Follow ethical research practices (OHSN-REB #20230428-01H)
- Respect EDI principles
- Maintain transparency in methods and data
