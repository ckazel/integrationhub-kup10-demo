# KUP-10 isolated deployment demo

This repository contains a separate demo service for IntegrationHubAI.
It has no Fenikstech code, domain, database, secrets, or deployment configuration.
All content is synthetic and public.

The manual GitHub Actions workflow deploys one exact approved commit to GitHub Pages.
`health.json` reports the deployed commit and its service state.
A successful deployment can have an unhealthy service state.
Datadog checks that state separately. An unhealthy response does not fail the deployment job.

Rollback deploys the known good commit through the same workflow.
The job succeeds only after the public target reports that commit.
Only one deployment runs at a time.

Run `node build.mjs` to build locally. Set `TARGET_SHA` to require an exact commit.
No custom domain is configured.

Official deployment contract:
https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages
