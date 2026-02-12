# OpenAPI Documentation — GitHub Pages

Interactive Swagger UI documentation for your APIs, auto-deployed via GitHub Pages.

## Quick Start

### 1. Enable GitHub Pages

Go to **Settings → Pages** in your repo and set:

- **Source**: `GitHub Actions`

The included workflow (`.github/workflows/deploy-pages.yml`) will auto-deploy on every push to `main`.

### 2. Add your specs

1. Drop your `.yaml` or `.json` OpenAPI files into the `specs/` directory
2. Edit the `SPECS` array in `index.html`:

```javascript
const SPECS = [
  { name: "My Service API", url: "./specs/my-service.yaml" },
  { name: "Another API",    url: "./specs/another-api.json" },
];
```

3. Commit and push — docs are live at `https://automatica-cluj.github.io/api-specs-repo/`

### 3. Deep-linking to a specific spec

You can link directly to a spec using a query parameter:

```
https://automatica-cluj.github.io/api-specs-repo/?spec=my-service
```

## Project Structure

```
├── index.html                          # Swagger UI page with spec selector
├── specs/                              # Your OpenAPI spec files go here
│   └── sample-petstore.yaml            # Sample spec (replace with yours)
├── .github/
│   └── workflows/
│       └── deploy-pages.yml            # Auto-deploy workflow
└── README.md
```

## Customization

- **Title**: Change the `<h1>` text in `index.html`
- **Theme**: Swagger UI supports custom CSS — modify the `<style>` block
- **Try It Out**: Enabled by default. Set `tryItOutEnabled: false` to disable.
- **Expand behavior**: Change `docExpansion` to `"none"`, `"list"`, or `"full"`

## Tips

- Keep spec files in `specs/` to stay organized
- Use YAML for readability, JSON if your tooling generates it
- The sample petstore spec can be safely deleted once you add your own
- For private repos, GitHub Pages requires a paid plan (Pro/Team/Enterprise)
