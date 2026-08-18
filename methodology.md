# About this data

Whimbrel Research tracks US medtech companies against the public record,
updated daily. Every published event carries the URL of the public
record it came from and can be checked in one click. Facts that cannot
be verified against a public source are not published. Company
identities are deduplicated, so one company is one history.

## Event kinds

- nih_award: NIH SBIR and STTR awards to small businesses, from NIH
  RePORTER.
- fda_clearance: FDA 510(k) clearances, from openFDA.
- fda_pma: FDA premarket approvals, from openFDA.

Company records served over MCP also carry patent_grant and
patent_application events from USPTO, and funding_filing events from
SEC Form D and Form C filings.

## Fields and dates

- Event ids are stable and scheme-prefixed (nih:, 510k:, pma:), so the
  same record re-read on a later day is the same event.
- Each event carries two dates: its own date from the source, and the
  observed date, which is when the event entered this archive.
  Registries publish on varying lags and the archive was seeded with
  history, so the two can differ widely; the event's own date is the
  authoritative one.
- amount_usd appears only when the source states a dollar figure.
  Nothing is estimated or summed.
- NIH award numbers are decoded mechanically into award_phase,
  award_year, and new_award (suffix year -01 is new money). Anything
  the number does not state stays absent.
- FDA events carry a browser URL (source_url) and a machine-fetchable
  api.fda.gov URL (source_url_api), because accessdata.fda.gov rejects
  non-browser user agents.

## Windows and caps

- signals-latest.json: the last 7 days.
- hot.json: companies with an event in the last 14 days.
- Company lookups over MCP (micro_brief, company_timeline): one per
  caller per day.

## What these files exclude

- Bulk history: the feed files show a rolling window. A company's full
  history is served one company at a time over MCP, with a daily
  lookup cap.
- People: no names or contacts, ever.
- Web finds: only government-registry events are published. Facts from
  articles and other web sources are held to a different verification
  standard and stay out.
- Fit judgments: nothing here matches companies to any firm. The
  buying-window level is a mechanical read of event freshness, not an
  assessment.

Free to cite with attribution to Whimbrel Research (whimbrelresearch.com). Every event links to the public record it came from. Contact: nate@whimbrelresearch.com
