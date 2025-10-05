# Public Health Environmental Surveillance Evaluation Framework (PHES-EF)

An international consensus study developing evaluation standards for wastewater-based surveillance using a multidisciplinary, multinational approach.

**Website**: https://big-life-lab.github.io/PHES-EF/

## About PHES-EF

The Public Health Environmental Surveillance Evaluation Framework (PHES-EF) is developing a consensus-driven evaluation framework for public health environmental surveillance, using wastewater surveillance as the primary example.

**Key Features:**
- Open science approach (CC-BY-SA-4.0 license)
- eDelphi consensus methodology
- International, multidisciplinary collaboration
- Emphasis on equity, diversity, and inclusion
- Registered protocol (Ottawa Health Science Network REB #20230428-01H)

## Repository Structure

```
PHES-EF/
├── _quarto.yml           # Quarto website configuration
├── *.qmd                 # Content pages (index, about, methods, delphi, etc.)
├── assets/               # Images, logos, SCSS themes, CSL files
├── data/                 # CSV data files (schema, example terms)
├── references.bib        # Bibliography
├── llm.md               # AI assistant instructions
└── docs/                 # Build output (auto-generated, do not edit)
```

## Requirements

### Software
- [Quarto](https://quarto.org/) (latest version recommended)
- TinyTeX: `quarto install tinytex`
- R >= 4.2.0 (compatibility floor for StatsCan/ICES environments)

### R Environment
This project uses **renv** for package management:

```r
# After cloning the repository
renv::restore()

# After adding new packages
renv::snapshot()
```

**Note**: Commit `renv.lock`, `.Rprofile`, and `renv/activate.R`. Do NOT commit `renv/library/`, `renv/staging/`, or `renv/local/`.

## Development Workflow

### Local Preview
```bash
quarto preview
```
Opens a live preview that updates as you make changes.

### Build Locally
```bash
quarto render
```
Generates static files in the `docs/` directory.

### Publishing
- **Automatic**: GitHub Actions publishes to GitHub Pages on push to main branch
- **Manual Setup**: Configure GitHub Pages to use `gh-pages` branch, root folder
  - Settings → Pages → Branch: `gh-pages`, Folder: `/`
  - The `gh-pages` branch appears after first successful publish

## Data Files

- [data/PHES-EF-schema.csv](data/PHES-EF-schema.csv) - Framework schema definition
- [data/PHES-ef-example-terms.csv](data/PHES-ef-example-terms.csv) - Example terminology

## Continuous Integration

- **Pull Requests**: Build check only (not published)
- **Main Branch**: Automatic deployment to GitHub Pages
- See [.github/workflows/](.github/workflows/) for workflow details

## Contributing

See [llm.md](llm.md) for AI assistant guidelines and development standards.

## Funding & Acknowledgments

This project is funded by:
- Canadian Institutes for Health Research (CoVaRR-Net, FRN: 175622)
- Health Canada (Safe Restart Agreement, #2223-HQ-000098)

The views expressed do not necessarily represent those of the funding organizations.

## License

CC-BY-SA-4.0 - See [LICENSE.md](LICENSE.md) for details.

## Contact

Visit the [Contact](https://big-life-lab.github.io/PHES-EF/contact.html) page or the [Team](https://big-life-lab.github.io/PHES-EF/team.html) page for more information.
