\# OpenAPI Documentation — GitHub Pages



Interactive Swagger UI documentation for your APIs, auto-deployed via GitHub Pages.



\## Quick Start



\### 1. Create a GitHub repo and push this folder



```bash

cd openapi-docs

git init

git add .

git commit -m "Initial API docs setup"

git remote add origin git@github.com:YOUR\_USER/YOUR\_REPO.git

git push -u origin main

```



\### 2. Enable GitHub Pages



Go to \*\*Settings → Pages\*\* in your repo and set:



\- \*\*Source\*\*: `GitHub Actions`



The included workflow (`.github/workflows/deploy-pages.yml`) will auto-deploy on every push to `main`.



\### 3. Add your specs



1\. Drop your `.yaml` or `.json` OpenAPI files into the `specs/` directory

2\. Edit the `SPECS` array in `index.html`:



```javascript

const SPECS = \[

&nbsp; { name: "My Service API", url: "./specs/my-service.yaml" },

&nbsp; { name: "Another API",    url: "./specs/another-api.json" },

];

```



3\. Commit and push — docs are live at `https://YOUR\_USER.github.io/YOUR\_REPO/`



\### 4. Deep-linking to a specific spec



You can link directly to a spec using a query parameter:



```

https://YOUR\_USER.github.io/YOUR\_REPO/?spec=my-service

```



\## Project Structure



```

├── index.html                          # Swagger UI page with spec selector

├── specs/                              # Your OpenAPI spec files go here

│   └── sample-petstore.yaml            # Sample spec (replace with yours)

├── .github/

│   └── workflows/

│       └── deploy-pages.yml            # Auto-deploy workflow

└── README.md

```



\## Customization



\- \*\*Title\*\*: Change the `<h1>` text in `index.html`

\- \*\*Theme\*\*: Swagger UI supports custom CSS — modify the `<style>` block

\- \*\*Try It Out\*\*: Enabled by default. Set `tryItOutEnabled: false` to disable.

\- \*\*Expand behavior\*\*: Change `docExpansion` to `"none"`, `"list"`, or `"full"`



\## Tips



\- Keep spec files in `specs/` to stay organized

\- Use YAML for readability, JSON if your tooling generates it

\- The sample petstore spec can be safely deleted once you add your own

\- For private repos, GitHub Pages requires a paid plan (Pro/Team/Enterprise)

