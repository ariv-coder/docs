# VoiceBook AI Documentation

This folder contains the documentation for VoiceBook AI, built with [Mintlify](https://mintlify.com).

## 📁 Structure

```
docs/
├── mint.json              # Mintlify configuration
├── introduction.mdx       # Landing page
├── quickstart.mdx         # Getting started guide
├── authentication.mdx     # Auth documentation
├── concepts/              # Core concepts
│   ├── agents.mdx
│   ├── calls.mdx
│   └── webhooks.mdx
├── integrations/          # Third-party integrations
│   ├── n8n.mdx
│   ├── zapier.mdx
│   └── make.mdx
├── api-reference/         # API documentation
│   ├── introduction.mdx
│   ├── calls/
│   ├── agents/
│   ├── phone-numbers/
│   └── webhooks/
├── logo/                  # Brand assets
│   ├── dark.svg
│   └── light.svg
└── favicon.svg
```

## 🚀 Local Development

### Prerequisites

- Node.js 18+
- npm or yarn

### Running Locally

```bash
# Install Mintlify CLI (if not already installed)
npm install -g mintlify

# Start the development server
cd docs
mintlify dev
```

The docs will be available at `http://localhost:3000`.

### Using npx (no install needed)

```bash
cd docs
npx mintlify dev
```

## 🌐 Deploying to Mintlify

### Option 1: Mintlify Dashboard (Recommended)

1. **Create a Mintlify account** at [mintlify.com](https://mintlify.com)

2. **Connect your repository**
   - Go to the Mintlify dashboard
   - Click "Add New Project"
   - Connect your GitHub repository
   - Select the `docs` folder as the root

3. **Configure the deployment**
   - Set the branch to deploy from (usually `main`)
   - Mintlify will auto-deploy on every push

4. **Custom domain (optional)**
   - In Settings > Custom Domain
   - Add your domain (e.g., `docs.voicebook.ai`)
   - Update your DNS with the provided CNAME

### Option 2: Manual Deployment

```bash
# Install Mintlify CLI
npm install -g mintlify

# Deploy from the docs folder
cd docs
mintlify deploy
```

You'll be prompted to authenticate with your Mintlify account.

## ⚙️ Configuration

The `mint.json` file controls the documentation configuration:

### Key Settings

```json
{
  "name": "VoiceBook AI",           // Site name
  "colors": {
    "primary": "#4F46E5"            // Primary brand color
  },
  "navigation": [...]               // Sidebar navigation
}
```

### Adding New Pages

1. Create a new `.mdx` file in the appropriate folder
2. Add frontmatter with `title` and `description`
3. Add the page path to `mint.json` navigation

Example:

```mdx
---
title: 'My New Page'
description: 'Description for SEO'
---

# My New Page

Content goes here...
```

Then in `mint.json`:

```json
{
  "navigation": [
    {
      "group": "Getting Started",
      "pages": ["introduction", "my-new-page"]
    }
  ]
}
```

## 📝 Writing Guidelines

### MDX Components

Mintlify provides several built-in components:

```mdx
<Note>Important information</Note>
<Warning>Careful about this</Warning>
<Info>Helpful tip</Info>
<Tip>Pro tip</Tip>

<Card title="Card Title" icon="rocket" href="/path">
  Card description
</Card>

<CardGroup cols={2}>
  <Card>Card 1</Card>
  <Card>Card 2</Card>
</CardGroup>

<Tabs>
  <Tab title="Tab 1">Content 1</Tab>
  <Tab title="Tab 2">Content 2</Tab>
</Tabs>
```

### API Reference Pages

Use these fields for API documentation:

```mdx
---
title: 'Create Resource'
api: 'POST https://api.voicebook.ai/v1/resources'
description: 'Create a new resource'
---

<ParamField body="name" type="string" required>
  The resource name
</ParamField>

<RequestExample>
```bash
curl -X POST ...
```
</RequestExample>

<ResponseExample>
```json
{ "id": "res_123" }
```
</ResponseExample>
```

## 🔗 Useful Links

- [Mintlify Documentation](https://mintlify.com/docs)
- [MDX Syntax Guide](https://mdxjs.com/docs/)
- [VoiceBook AI Dashboard](https://voicebook.ai/dashboard)
- [API Status](https://status.voicebook.ai)

## 🐛 Troubleshooting

### Common Issues

**"Page not found" errors**
- Ensure the page is listed in `mint.json` navigation
- Check file path matches exactly (case-sensitive)

**Styles not loading**
- Clear browser cache
- Restart the dev server

**Build errors**
- Check MDX syntax (unclosed tags, etc.)
- Validate `mint.json` is valid JSON

### Getting Help

- Open an issue in this repository
- Contact support@voicebook.ai
- Join our [Discord community](https://discord.gg/voicebook)
