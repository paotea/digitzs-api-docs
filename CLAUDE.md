# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Mintlify documentation site. Mintlify is a documentation platform that uses MDX files and a central `docs.json` configuration file to generate beautiful, interactive documentation websites.

## Essential Commands

### Local Development
- **Start dev server**: `mint dev` (runs on http://localhost:3000 by default)
- **Custom port**: `mint dev --port 3333`
- **Update CLI**: `mint update` or `npm update` (if dev environment isn't running or doesn't match production)
- **Validate links**: `mint broken-links` (identifies broken links in documentation)

### Installation
- **Install Mintlify CLI globally**: `npm i -g mint`
- **Remove CLI**: `npm remove -g mint`

### Prerequisites
- Node.js version 19 or higher required

## Architecture and Structure

### Configuration Hub
- **`docs.json`**: Central configuration file that controls:
  - Site theme, name, colors, favicon, and logo
  - Navigation structure (tabs, groups, pages)
  - Global anchors and navbar links
  - Footer socials
  - Contextual features (copy, view, AI integrations)

All navigation and page organization is defined here. When adding new pages, they must be registered in the `navigation` section of `docs.json`.

### Content Organization
- **MDX files**: All content pages use MDX (Markdown + JSX components)
- **Root level**: Primary navigation pages (index.mdx, quickstart.mdx, development.mdx)
- **Subdirectories**: Organized by topic
  - `essentials/`: Core documentation features (settings, navigation, markdown, code, images, snippets)
  - `api-reference/`: API documentation and endpoint examples
  - `ai-tools/`: AI tool integration guides
- **Assets**:
  - `snippets/`: Reusable MDX content snippets
  - `images/`: Image assets
  - `logo/`: Light and dark mode logo variants
  - `favicon.svg`: Site favicon

### Navigation Pattern
The site uses a two-level tab structure defined in `docs.json`:
1. **Tabs**: Top-level navigation (e.g., "Guides", "API reference")
2. **Groups**: Sections within tabs that contain related pages

### Adding New Pages
1. Create the `.mdx` file in the appropriate directory
2. Add the page path (without .mdx extension) to the `navigation.groups[].pages` array in `docs.json`
3. Ensure frontmatter includes `title` and `description`

## Mintlify-Specific Components
MDX files can use Mintlify's built-in components like:
- `<Card>`, `<CardGroup>`, `<Columns>`
- `<Accordion>`, `<AccordionGroup>`
- `<Tip>`, `<Note>`, `<Warning>`, `<Info>`
- `<Steps>`, `<Step>`
- `<Frame>` for images
- `<Snippet>` for reusable content

## Deployment
Changes pushed to the main branch are automatically deployed via Mintlify's GitHub app integration. No manual deployment needed.

## Troubleshooting
- If encountering "sharp" module errors on darwin-arm64: Remove CLI, upgrade to Node v19+, reinstall CLI
- For unknown errors: Delete `~/.mintlify` folder and run `mint dev` again
- If preview doesn't match production: Run `mint update`
