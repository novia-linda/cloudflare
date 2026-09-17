# demo-tanja-bing

Ren statisk testsida för Bing-indexering och Microsoft Copilot.

## Struktur

- `wrangler.jsonc` – låser Worker-namnet och säger åt Cloudflare att bara publicera `./public/`.
- `public/index.html` – testsidan.
- `public/robots.txt` – tillåter crawling och pekar på sitemap.
- `public/sitemap.xml` – listar testsidans kanoniska URL.

## Viktigt

Skapa GitHub-repot med namnet `demo-tanja-bing` och använd samma Worker-namn i Cloudflare. Då blir den avsedda adressen:

`https://demo-tanja-bing.noviaaiforbusiness.workers.dev/`

Om Worker-namnet ändras måste URL:en även ändras i `public/index.html`, `public/robots.txt` och `public/sitemap.xml`.

## Cloudflare

- Build command: lämna tomt
- Deploy command: `npx wrangler deploy`
- Root directory: `/`
- Production branch: `main`

`wrangler.jsonc` gör att bara `public/` laddas upp som statiska assets. `.git` och andra repofiler publiceras inte.
