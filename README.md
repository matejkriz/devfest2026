# DevFest 2026 · Your app, their data

Slides and resources for Matěj Kříž's talk, **Local-first with Evolu**.

Website: https://devfest2026.matejkriz.cz

Vercel URL: https://devfest2026-blue.vercel.app

A static site built with HTML and CSS. No dependencies or build step. Vercel Web Analytics measures page views with a deferred script.

Web Analytics is enabled for this project on the Hobby plan. Its initialization lives in `public/analytics.js`, so the existing Content Security Policy can keep blocking inline scripts. The tracking script is served by Vercel at `/_vercel/insights/script.js`; it is unavailable in the local Python preview.

## Run locally

From the repository root:

```sh
python3 -m http.server 8080 --directory public
```

Open http://localhost:8080.

## Update resources

Edit the resource list in `public/index.html`. Each `<li>` contains a title, credit, format, description, and destination URL. Keep the visible numbers sequential.

## Update the slides

Export the Keynote deck as a PDF without presenter notes and replace:

```
public/downloads/your-app-their-data.pdf
```

PDF preserves the slide layout and works without Keynote or PowerPoint. Animations and transitions are not included.

## Deploy

Import this repository into Vercel. `vercel.json` selects `public` as the output directory. Use the Other framework preset with no build or install command.

Connect `devfest2026.matejkriz.cz` in the Vercel project's domain settings. Pushes to `main` deploy automatically once the Git integration is connected.

The project and Git integration are connected. The custom domain still needs this record at the authoritative DNS provider, Forpsi:

| Type | Name | Target |
| --- | --- | --- |
| CNAME | `devfest2026` | `cname.vercel-dns.com` |

Replace a conflicting record for this subdomain if one exists. Keep unrelated records and the domain's nameservers unchanged. The Vercel URL works while the DNS change is pending.

The illustration comes from the original presentation. The linked articles and videos belong to their respective authors.
