# Mode: pipeline — Pending URL inbox

Use `data/pipeline.md` as an inbox for jobs worth reviewing later.

The user can drop URLs there whenever they want, then ask to process the inbox in one pass.

## Workflow

1. Read `data/pipeline.md`
2. Find unchecked items in the pending section
3. For each pending job URL:
   - determine the next report number
   - extract the JD from browser/fetch/search fallbacks
   - run the full evaluation flow
   - generate a tailored PDF if the role is worth pursuing
   - write the tracker addition
   - mark the pipeline item as processed with outcome summary
4. Return a summary table at the end

## Summary format

```text
| # | Company | Role | Score | PDF | Recommendation |
```

## Suggested pipeline.md format

```markdown
## Pending
- [ ] https://jobs.example.com/posting/123
- [ ] https://boards.greenhouse.io/company/jobs/456 | Company Inc | Senior Product Manager
- [!] https://private.url/job — login required

## Processed
- [x] #143 | https://jobs.example.com/posting/789 | Acme Corp | Product Operations | 4.3/5 | PDF ✅
- [x] #144 | https://boards.greenhouse.io/xyz/jobs/012 | BigCo | Solutions | 2.8/5 | PDF ❌
```

## JD extraction strategy

Use this order:
1. browser automation for JS-heavy or SPA pages
2. static fetch for simpler pages
3. search fallback if the main page is inaccessible

Special cases:
- LinkedIn often requires login → ask for pasted text if extraction fails
- PDF URLs should be read directly
- local files may be referenced with `local:` prefixes

## Parallelism note

If processing multiple roles, parallelize only where it does not create browser contention.
Do not run multiple browser-dependent extraction flows in parallel against a shared browser instance unless the execution environment supports it safely.

## Sync check

Before processing a batch of URLs, run:

```bash
node cv-sync-check.mjs
```

If the profile / resume setup is incomplete, stop and fix that first.
