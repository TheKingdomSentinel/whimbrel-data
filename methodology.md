# About this data

Whimbrel Research tracks US medtech companies against the public record,
updated daily. Every published event carries the URL of the public
record it came from and can be checked in one click. Facts that cannot
be verified against a public source are not published. Company
identities are deduplicated, so one company is one history.

## Event kinds

- nih_award: NIH SBIR and STTR awards to small businesses, from NIH
  RePORTER. Published only when the award's own text describes a
  medical device, diagnostic instrument, or medical software program;
  NIH small-business awards for drugs, biologics, and basic science
  are collected but not published, because this is a medtech feed.
- fda_clearance: FDA 510(k) clearances, from openFDA.
- fda_pma: FDA premarket approvals, from openFDA.

Company records served over MCP also carry patent_grant and
patent_application events from USPTO, and funding_filing events from
SEC Form D and Form C filings.

## People

An event carries the people the registry itself names in that record,
and nobody else: principal investigators on an NIH award, the contact
on a 510(k), officers on an SEC filing, officials on a trial
registration. Each name is already public in the source the event
links to, and appears here with the role that source states.

What is never here: email addresses, phone numbers, titles or
affiliations that were inferred rather than stated, and anyone the
record does not name. Researched leadership and contact routes are a
different thing built a different way, and they are not in these
files; they come from the deep-research layer.

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

- signals-latest.json: the last 14 days.
- Company lookups (micro_brief, company_timeline, and the /v1/company
  routes): 100 per caller per day, and
  2000 across all free callers per
  day.
- find_signals searches the whole archive and does not count as a
  company lookup.
- Every free call, the cheap ones included, counts against a ceiling of
  600 per caller per day. It is far above a real
  reader's day and exists to bound one caller's cost, not to ration.

## What these files exclude

- Bulk history: the feed files are a rolling window. The archive
  behind them is searchable a query at a time (find_signals) and a
  company at a time (micro_brief, company_timeline) under the caps
  above; it is not published as a bulk download.
- Contact details: see People above. Names as a registry states them,
  never a route to reach someone.
- Web finds: only government-registry events are published. Facts from
  articles and other web sources are held to a different verification
  standard and stay out.
- Judgments: no fit assessments, no matching, and no computed ratings
  of any kind. These files carry events and dates only. What they mean
  for a particular firm is the work of the paid layer, where matching
  runs against a stated capability profile, or of an engagement.

Free to cite with attribution to Whimbrel Research (whimbrelresearch.com). Every event links to the public record it came from. Contact: nate@whimbrelresearch.com
