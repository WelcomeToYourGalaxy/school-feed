# school-feed

A live wire on schooling worldwide: who owns it, who writes what is taught,
what it costs, what it does with the people inside it, and what it is for.

Built after the School subsection of *Economic Inequality Within It* on
Welcome to Your Galaxy, and scoped to the subjects raised there.

## What it does

`harvest_school.py` reads 166 wires every two hours — education ministries and
inspectorates, the OECD and the World Bank, research institutes, unions and
corporate-accountability groups, and Google News across 26 languages — and
writes `wire_school.json`. `index.html` renders it; the Weebly embed carries
the same document inside an iframe.

Standard library only. No dependencies, no API keys, no model calls. Nothing is
written or summarised: headlines and snippets are the publishers' own and every
row links to the original.

## The twenty-four subjects

| | |
|---|---|
| The factory model and its purpose | Curriculum homogenisation |
| Local and Indigenous knowledge | The textbook oligopoly |
| Mergers and market consolidation | Private equity in education |
| Privatisation of public schooling | For-profit colleges and diploma mills |
| Student debt and the price of entry | Credential inflation |
| The elite university pipeline | Capture of global education governance |
| Corporate partnership with the state | Edtech contracts and vendor lock-in |
| Knowledge behind a paywall | Student data as an asset |
| Ecosystem conditioning | Teachers replaced by technology |
| The testing industry | Teachers and their conditions |
| What may be taught | What schools invest in |
| Who gets in and who is kept out | Learning outside the system |

## The gate

Every subject term carries the context words it must appear beside, so a sports
result or a prize day cannot reach the wire. School life as an event listing is
refused, as is sponsored ranking and discount copy. Campus policing belongs to
the law enforcement wire.

## Weight

Each story is scored on what it carries: a decision (2), institutional material
(2), a measured figure (1), a pending decision with a date (1), a named
jurisdiction (1), a primary source (1). At three or more it is marked
consequential.

## Sources

`sources_school.json` has three blocks. `direct` holds feed URLs proven working
in the sibling repos — nothing in it was guessed, because an untested feed URL
reports itself unreachable on every harvest and quietly makes the coverage
figure a lie. `gnews` is Google News locale searches, whose URLs the harvester
builds from `hl`/`gl`/`ceid`. `events` is subject searches for institutions the
section names but which have no verified feed here — UNESCO, the Global
Partnership for Education, the publishers, the private equity owners.

To add a source, put it in `direct` with a feed URL you have actually opened.

## Running it

    python3 harvest_school.py
    python3 harvest_school.py --dry-run
    python3 verify_sources.py
