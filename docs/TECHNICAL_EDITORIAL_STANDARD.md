# Technical editorial and code-example standard

Tech Blog publishes technical explanations that readers may use in production or personal projects. A polished article is not a sufficient signal of correctness: examples must be reproducible, assumptions stated and source claims traceable.

## Recommended article structure

1. **Problem:** what the reader is trying to accomplish and where this approach applies.
2. **Prerequisites:** language, runtime, dependencies, environment and version constraints.
3. **Minimal example:** the smallest original example that demonstrates the behavior.
4. **Explanation:** why the result follows, what assumptions matter, and common failure modes.
5. **Validation:** the command and observed output; differentiate tested results from illustrative excerpts.
6. **Trade-offs:** performance, accessibility, security and compatibility implications where relevant.
7. **References:** primary docs/specifications or directly examined sources with dates as needed.
8. **Updates:** correction history when important technical behavior changes.

Do not publish copy-pasted documentation as original prose or assert that untested snippets have been executed.

## Claims and source hygiene

| Claim type | Review requirement |
| --- | --- |
| API behavior | Verify against the library's specific documented version |
| Security guidance | Link authoritative advisory/official guidance and identify affected versions |
| Performance numbers | Show device, method, measured period and sample context |
| Product compatibility | State tested environments and known limitations |
| Tutorials | Make steps self-contained, with required commands and expected outcomes |
| External figures | Cite source and date; never invent metrics or quotes |

When the current version cannot be established, make the uncertainty visible instead of guessing.

## Site-level acceptance

The repository exposes **index.html** and **blog_detail.html** with assets under **assets/**. Confirm navigation and article links resolve, code blocks remain readable on mobile, heading order is logical, link text is meaningful, media has appropriate alternatives, and the pages provide distinct titles and descriptions. Existing **robots.txt** should not be changed without checking intended indexing behavior.

## Preview and verification

Use a static server from repository root:

~~~bash
python -m http.server 8000
~~~

Then inspect http://localhost:8000/ and the article-detail page. This verifies local rendering only, not that an external command/example is correct. Run each changed snippet in the declared runtime and record version and observed output in its PR.

## Reviewer submission requirements

Provide article paths, original sources, version assumptions, verified example outputs, semantic/visual checks, broken-link results, copyright/attribution status and an edit/correction plan. Use synthetic examples and never publish real API tokens.

## Corrections

Fix high-impact misinformation quickly, document what changed and why, and check any code samples or SEO snippets that repeat the same claim. Preserve an intelligible correction note instead of silently replacing a historical assertion.
