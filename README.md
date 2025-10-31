# Digitzs API Documentation

Official API documentation for the Digitzs payment processing platform, built with Mintlify.

## Overview

This repository contains the complete documentation for the Digitzs API, which provides merchant services including payment processing, merchant account management, and transaction handling. The documentation is built using [Mintlify](https://mintlify.com), a modern documentation platform.

## What's Included

- **Getting Started Guide**: Introduction to the Digitzs API and quick start instructions
- **Authentication Guide**: Complete authentication flow with API key and token generation
- **API Reference**: Comprehensive documentation for all API endpoints
  - Authorization endpoints (2)
  - Payment endpoints (9)
  - Merchant endpoints (5)
- **Error Codes**: Detailed HTTP error code reference with solutions

## Local Development

### Prerequisites
- Node.js version 19 or higher

### Installation

Install the Mintlify CLI globally:

```bash
npm i -g mint
```

### Preview Locally

Navigate to the repository root and run:

```bash
mint dev
```

Your documentation will be available at `http://localhost:3000` with live reload enabled.

### Custom Port

To run on a different port:

```bash
mint dev --port 3333
```

### Validate Links

Check for broken links in the documentation:

```bash
mint broken-links
```

## Documentation Structure

```
.
├── index.mdx                    # Main landing page
├── authentication.mdx           # Authentication guide
├── quickstart.mdx              # Quick start tutorial
├── error-codes.mdx             # Error reference
├── docs.json                   # Mintlify configuration
└── api-reference/
    ├── overview.mdx            # API overview
    ├── authorization/          # Auth endpoints
    │   ├── overview.mdx
    │   ├── create-key.mdx
    │   └── create-token.mdx
    ├── payments/               # Payment endpoints
    │   ├── overview.mdx
    │   ├── create-ach-payment.mdx
    │   ├── create-token-payment.mdx
    │   ├── create-split-payment.mdx
    │   ├── create-second-split.mdx
    │   ├── refund-void.mdx
    │   ├── refund-split.mdx
    │   ├── get-by-id.mdx
    │   ├── get-status.mdx
    │   └── list.mdx
    └── merchants/              # Merchant endpoints
        ├── overview.mdx
        ├── create.mdx
        ├── get-by-id.mdx
        ├── list.mdx
        ├── update-bank-info.mdx
        └── update-avs-mode.mdx
```

## Deployment

Changes pushed to the main branch are automatically deployed via Mintlify's GitHub app integration. No manual deployment is required.

To set up automatic deployment:
1. Install the Mintlify GitHub app from your [dashboard](https://dashboard.mintlify.com/settings/organization/github-app)
2. Connect this repository
3. Push changes to the main branch

## Troubleshooting

### Error: Could not load the "sharp" module

This may be due to an outdated version of Node.js:
1. Remove the CLI: `npm remove -g mint`
2. Upgrade to Node v19 or higher
3. Reinstall the CLI: `npm i -g mint`

### Unknown Errors

1. Delete the `~/.mintlify` folder
2. Run `mint dev` again

### Preview Doesn't Match Production

Update the CLI to the latest version:

```bash
mint update
```

## Resources

- [Mintlify Documentation](https://mintlify.com/docs)
- [Digitzs API User Manual](https://digitzs.com/wp-content/uploads/2019/04/API-User-Manual.pdf)
- [Digitzs Quick Start Guide](https://digitzs.com/wp-content/uploads/2019/07/Digitzs-Quick-Start-Guide.pdf)

## Support

For questions or issues with the Digitzs API, contact support@digitzs.com

## License

See [LICENSE](LICENSE) file for details.
