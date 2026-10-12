# ARO IQ — public dashboard site

Static, public deployment of the **ARO IQ Educational Intelligence** demo dashboard.

The site is a single self-contained HTML file (`index.html`) exported from the
ARO IQ Build Package (`build/consumption/aro_iq_dashboard.html`). It embeds the
**synthetic SYN001 dataset only** — there is no real student PII, no backend and
no database. Everything (data, logo, photos, scripts) is inlined.

## Hosting

- Deployed on **Vercel** as a static site (no build step).
- `vercel.json` disables framework detection and sets basic security headers.
- Pushes to the default branch auto-deploy to production.

## Updating the dashboard

1. Rebuild the artifact in the Build Package:
   `powershell -File build/consumption/build_artifact.ps1 -EmbedJson <embed.json>`
2. Copy the rebuilt `build/consumption/aro_iq_dashboard.html` over `index.html` here.
3. Commit and push — Vercel redeploys automatically.

## Data notice

Synthetic demonstration data. Names, results, attendance and photos are
fabricated and do not represent real learners.
