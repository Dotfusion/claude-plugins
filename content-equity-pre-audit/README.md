# Content Migration Audit

A large scale content migration stalls on one question: what do we do with each page? This plugin answers it for your content team before the platform work starts. It scores every page on the content equity it has already earned (search, AI answers, visits) and gives each one a verb with the rule behind it, plus the redirect map and the work queue that fall out of those verbs.

## What it does

Name your site, or paste your Google Analytics, Search Console or crawl export, and the audit scores each page on four independent 1 to 5 scales (search equity, AI answer presence, visits, and a column your team fills) and assigns one of six verbs by rules you can repeat in a meeting:

| Verb | Meaning |
| --- | --- |
| Keep | Moves to the new site as is |
| Consolidate | Merges into another page |
| Rewrite | URL and purpose survive, content gets redone |
| Redirect | Page dies, equity passes to a mapped destination |
| Retire | Page dies, nothing replaces it |
| Create | Net-new content the site needs and does not have |

Every row shows the rule that fired and whether its scores were measured, proxied or missing. You get a verdict card, the scored inventory, a content model preview (candidate models for the page types that repeat, with the fields they share), a redirect map, a work queue grouped by who acts on it (writers, the migration team, the decision owner), a methodology note you can forward, and a review pile for the calls that need a human.

Four ways to run it:

- **Connected tools.** If you have a Google Analytics, Search Console or Screaming Frog connector set up in Claude, the plugin pulls the reports itself and scores every URL as measured data. Nothing to export.
- **Export mode.** Paste a GA4 landing-page export, a Search Console pages export, or a Screaming Frog crawl. Every URL in the file is scored, no cap.
- **Sample mode.** Just name the site. The plugin fetches a 30-page sample and extends it in batches if you ask.
- **Portfolio mode.** Give it a list of domains, such as a set of property or brand microsites. It samples each one and shows which shared-template pages repeat across the estate.

## How to use it

Install from the Claude directory (Customize > Plugins > Discover), or in Claude Code:

```
/plugin install dotfusion-content-equity --marketplace dotfusion/claude-plugins
```

Then ask, for example:

- "Run a content migration audit on example.com."
- "Here is our Search Console pages export for the last 16 months. Which of these 6,000 URLs are safe to cut?"
- "These are our 12 property sites. Which pages are duplicated across all of them?"

The skill confirms scope in three lines before it starts, then works through the sample or the export. A complete example run on dotfusion.com is in the repository's [examples folder](https://github.com/Dotfusion/claude-plugins/tree/main/examples).

## What it does not do

It does not promise rankings, traffic recovery or AI visibility after migration. It does not estimate a number it cannot see: without your exports, the Visits column reads "no data" and the SEO column is a labelled proxy from on-page signals. It cannot query ChatGPT, Perplexity or Google AI Overviews, so the AI answer column is either your pasted visibility report or a labelled proxy from Claude's own web search. It does not add domains it discovers without asking you.

## Data

The plugin has no servers of its own and bundles no connectors. It asks Claude to fetch pages on the domain you name using Claude's web fetch tool, to read any file you paste within your conversation, and, if you have connected them yourself, to read your Analytics, Search Console or Screaming Frog data through those connectors. Nothing is sent to Dotfusion. Audit only sites you own or are authorized to audit.

## Who built it

[Dotfusion](https://dotfusion.com) is a 27-year-old B Corp in Toronto. We migrate enterprises off AEM, Sitecore and WordPress onto composable platforms, and this is the method we run at the start of those projects, published under MIT so anyone can use it. Support: plugins@dotfusion.com. Privacy: https://dotfusion.com/privacy.

## License

MIT. Use it, adapt it, improve it.
