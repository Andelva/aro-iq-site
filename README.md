# ARO IQ — public demo redirect

This repo used to hold a static, single-file export of the ARO IQ demo dashboard. That page has been
**replaced by a redirect** to the live .NET sandbox, which runs the real application against a
fictitious-data database on Azure (NZ North):

**https://aroiq-sandbox-nz.azurewebsites.net/**

- `vercel.json` issues a temporary (307) redirect for every path to the sandbox root. It is temporary on
  purpose, so browsers do not cache it if the destination changes (e.g. to a custom domain).
- `index.html` is a tiny fallback (meta refresh + link) for clients that ignore redirects.
- The old static dashboard is preserved in git history (commit before the redirect). To restore it, revert the
  redirect commit and push; Vercel redeploys automatically.

The sandbox is built and operated from the ARO IQ platform repository (`Andelva/aro-iq`, `build/sandbox/`).
It contains **fictitious data only** — no real learner information.
