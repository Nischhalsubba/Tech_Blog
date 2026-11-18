# Article evidence and navigation audit

## Repository reality
The site is a static `index.html` and `blog_detail.html` backed by `assets/`. The article page references external imagery and hard-coded targets; for example, the inspected article navigation includes destinations such as `contact-us.html`, `about-us.html` and `pricing.html` that are not present among repository-root HTML entries. Review every target before presenting the navigation as complete. This file is a QA protocol, not proof that those links are currently live.

## Publication contract
Every technical article should record, privately or in approved public metadata: author, review date, claim sources, tested runtime/platform, last verified date and any known version limitations. Do not assign invented publication dates or claim testing based on a code snippet alone.

| Content element | Acceptance |
| --- | --- |
| Title and summary | Accurately describe the article's real subject |
| Factual claim or quoted statistic | Traceable primary source and observation date |
| Code or configuration | Exact environment and reproducible test commands |
| Security instruction | Safe defaults, explicit scope and threat model |
| Images and illustrations | Credit/permission, meaningful alt text, reliable hosting |
| External source link | Valid destination and relevance at review time |
| Internal navigation | Existing target or documented redirect |
| SEO metadata | Canonical route and dates consistent with published content |

## Repeatable link and behavior test
1. Start `python3 -m http.server 8000` in the repository root.
2. Load `index.html` and `blog_detail.html`; record request failures and console warnings.
3. Extract and review anchors from header, footer, cards, breadcrumbs and in-article links. Differentiate `#` mock actions from actual destinations.
4. Check local targets on a case-sensitive filesystem. Flag missing HTML paths; never silently replace them with guessed URLs.
5. Inspect remote media loading, fallback behavior and permission/credit context.
6. Navigate with keyboard at narrow viewport and increased text size. Check readable paragraphs, code overflow, focus order and headings.
7. For technical content, independently execute supported code examples in a clean environment, recording versions and expected output.
8. Review `robots.txt` and any sitemap/canonical assumptions against the actual publish destination.

## Editorial and release record
```text
PR / page / author / reviewer:
Sources and observation dates:
Runnable examples, command and versions:
Internal and external links tested:
Keyboard/mobile/zoom results:
Image permission/alt/hosting evidence:
Metadata and canonical review:
Open defects and severity:
Deploy URL, date and rollback commit:
```

## Ship blockers
Do not publish broken core navigation, fabricated author or outcome data, untested dangerous code, inaccessible essential diagrams, or external material without necessary rights. If a resource disappears, update the article with a dated correction or remove the unsupported claim.

## Scope
Only the maintainers' audit process is added. The current HTML is not altered or certified; fixing the observed link issues belongs in independently reviewed implementation work.
