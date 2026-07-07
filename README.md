# clactoncandidates.co.uk

Independent, non-partisan voter-information site for the 2026 Clacton by-election,
triggered by Nigel Farage's resignation as MP on 7 July 2026.

Built with [Astro](https://astro.build) as a fully static site — zero client-side
JavaScript, no webfonts, no analytics. Deployed on Vercel.

## Updating content

All content lives in JSON files under `src/data/`. Edit, commit, push — Vercel
redeploys automatically in under a minute. No code changes needed for:

| To do this | Edit |
|---|---|
| Add/update a candidate | `src/data/candidates.json` — add an entry (see the Farage entry for the shape). Set `status` to `declared`, `expected`, `nominated`, or `withdrawn`. Parties with no candidate automatically show an "awaiting" card. |
| Set the polling date / deadlines | `src/data/election.json` — fill in `pollingDay` and the `keyDates` entries (ISO dates). Every "TBC" on the site switches to the real date. |
| Add/update a party | `src/data/parties.json` |
| Update issue summaries | `src/data/issues.json` |
| Extend the timeline | `src/data/timeline.json` |

Candidate photos go in `public/images/candidates/` and are referenced by the
`photo` field.

## Development

```sh
npm install
npm run dev       # dev server at localhost:4321
npm run build     # static build to dist/
npm run preview   # serve the build locally
```

## Deploying

Push the repo to GitHub, import it at [vercel.com/new](https://vercel.com/new)
(Astro is auto-detected), then add `clactoncandidates.co.uk` under
Project → Settings → Domains and set the DNS records Vercel shows at your
registrar.

## Editorial policy

Strictly neutral: no endorsements, every factual claim sourced, every candidate
on the ballot offered the same space on the same terms. See `/about` on the site.
