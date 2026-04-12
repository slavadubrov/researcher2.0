# Knowledge Maintenance

The knowledge base ([[concepts]] and [[data-points]]) is the compound interest engine of this system. But stale data is worse than no data — it creates false confidence. This file defines how to keep the knowledge base useful as it grows.

> **Lineage:** This adapts the intelligence community's source validation cycles and library science principles of collection management. Also draws on software engineering's concept of technical debt — unmaintained knowledge accumulates "knowledge debt" that eventually undermines new analysis. Key lesson from IC collection management: the cost of maintaining a knowledge base is always underestimated, and the cost of NOT maintaining it is always discovered too late.

## Review Cycle

### Per-Project Review
After every project, before closing:
- Check: did any existing data points contradict what you found? if so, update or flag them
- Check: are any concepts defined differently than how this project used them? reconcile
- Add date stamps to all new entries

### Periodic Audit (Every 5 Projects)
- Scan all data points older than 1 year: are they still current?
- Flag any data point whose source is no longer accessible
- Check for duplicate or near-duplicate entries
- Look for entries that have never been referenced in a project — consider removing

### Annual Review
- Audit all entries for continued relevance
- Remove or archive data points that are clearly outdated
- Review category structure: does it still match the topics you research?

## Freshness Indicators

Every data-point entry should include:

```
- **Metric**: [value] — [source, date, tier]
- Collected: [date added to knowledge base]
- Expires: [date after which this should be re-verified, or "stable" for constants]
- Status: current / needs-review / deprecated
```

### Expiry Guidelines
- Economic statistics (GDP, rates, prices): expires after 1 year
- Demographic data (population, fertility): expires after 3 years
- Scientific constants and established findings: mark as "stable"
- Policy positions and political stances: expires after 6 months
- Technology benchmarks: expires after 1 year

## Deprecation Rules

When a data point is outdated:
1. Do NOT delete immediately — mark as `Status: deprecated` with reason
2. If a newer value exists, add the new entry and link to the deprecated one
3. Deprecated entries stay for 2 review cycles, then can be removed
4. If an entire domain becomes irrelevant, archive the entries to a separate file rather than deleting

## Scaling Strategy

### Under 50 Entries (Current State)
- Single `concepts.md` and `data-points.md` files work fine
- Use `---` dividers between domains

### 50-100 Entries
- Add category headers within files (## Economics, ## Demographics, ## Technology, etc.)
- Add a table of contents at the top of each file

### Over 100 Entries
- Split into domain-specific files: `knowledge/economics.md`, `knowledge/demographics.md`, etc.
- Keep a master `knowledge/index.md` that links to all domain files
- Each domain file follows the same entry format

### Tagging Convention
When entries reference multiple domains, use inline tags:
```
- **Metric**: [value] — [source, date, tier] #economics #demographics
```

## Connects To
- [[concepts]] — the concept knowledge base
- [[data-points]] — the data knowledge base
- [[source-evaluation]] — source tier informs data point reliability
- [[index]] — knowledge maintenance is part of the post-research workflow
