## The Arbiter Project

Problem solving that shows its work, in any domain: every finding, forecast and plan says what it checked, what it
assumed and what it could not.

**Silence reads as health.** Most checkers answer one question, what is wrong, and when they return nothing you cannot
tell whether they looked and found nothing or never looked at all. Those two results are printed identically, and
only one of them is good news. The engine separates them. A verdict carries what was found, what was not checked and
the reason, how many checks were tried, and what the model never asked, so a clean result means *these checks were
tested and held* and is distinguishable from *nothing was testable*.

**Where this came from.** The project began in 2025 as an AI bot answering OpenBMC questions in GitHub issues; it is
archived. In 2026 it became a closed-loop orchestrator with a digital twin, run for eleven days under scheduled
faults. A person found sixteen surprises in that run, and the detector surfaced none of them at the time; the evidence
pack that says so is published with the engine, findings against the project included. The engine was cut from that
orchestrator and released in August 2026, as a detection engine that reports what it did not check.

**Declared, not learned.** A domain is written down first, what exists, what is observed on it, what must hold, and
[the engine](https://github.com/james-sheen/arbiter) checks against that declaration; it infers nothing from a
property's name, its units or a correlation between two series. A deviation from a line somebody declared is a
statement about the system; a deviation from a baseline the engine inferred is a statement about the last N samples.
It finds violations of what you declared and does not discover what you did not think of; modelling a real system is
your work. Over time the same rule catches a quiet failure: a limit that moved reads exactly like a part that
recovered, unless the line is declared, dated and compared.

**One engine, your vocabulary.** The engine evaluates eight axioms, declared per indicator in a domain model and not
in code, over a typed graph. The family's domain-free core,
[presence-audit](https://github.com/james-sheen/presence-audit), names no domain at all, and a test holds it to that;
it says one of three things about a declared point: reading, present but not reading, or absent. Every tool in the
family exits the same way: clean, worse, or could not complete, where could not complete outranks worse. The domains
so far: a server's firmware ([bmc-sensor-audit](https://github.com/james-sheen/bmc-sensor-audit),
[cert-generator](https://github.com/james-sheen/cert-generator),
[fleet-sensor-baseline](https://github.com/james-sheen/fleet-sensor-baseline)); a factory line read over OPC UA
([factory-line-audit](https://github.com/james-sheen/factory-line-audit)); a statement of work's deliverables
([engagement-deliverable-audit](https://github.com/james-sheen/engagement-deliverable-audit)); a period's financial
filings ([filing-balance-audit](https://github.com/james-sheen/filing-balance-audit)); an organisation's operating
model ([operating-health-audit](https://github.com/james-sheen/operating-health-audit)); a margin book's forecasts
([margin-book-audit](https://github.com/james-sheen/margin-book-audit)); and two public records, a country's air
traffic control facilities and a state's nursing homes
([appendix B](https://github.com/james-sheen/absent-is-not-healthy/tree/master/appendix-b)).

**Beyond detection, the same books.** A forecast made elsewhere is filed as a claim to be audited: the eight axioms
run over it, and it is scored against a baseline the forecaster did not choose. An action somebody took is recorded
as a prediction and graded by the readings that followed. A plan says what each candidate does to each open case, and
doing nothing is always a candidate. Measuring and proposing are the engine's; declaring is the author's. A world
model predicts, and this audits.

## Absent is not healthy

A server's baseboard management controller reports its sensors, and a reader that waits for a reading to cross a
line learns nothing from a sensor that reports nothing: silence reads as health. The report checks what a board's
configuration declares against what its firmware reports – on OpenBMC's public configuration corpus and on
upstream firmware – and follows the result into the documents a factory hands a buyer. It is the first domain
carried end to end, from the declaration to the acceptance certificate.

**The report**, version 1.0, CC BY 4.0: [DOI 10.5281/zenodo.23585862](https://doi.org/10.5281/zenodo.23585862) ·
[its source, claims ledger and case studies](https://github.com/james-sheen/absent-is-not-healthy)

**Upstream**: the two contradictory thresholds it found, filed as
[`entity-manager` issue #38](https://github.com/openbmc/entity-manager/issues/38).

### Posts

*Each is listed with the day it goes out, and becomes a link that day.*

- **[Absent is not healthy](https://github.com/james-sheen/absent-is-not-healthy/blob/master/posts/2026-11-03-absent-is-not-healthy.md)**
  – what OpenBMC's configuration corpus declares, and what upstream firmware reports.
  3 November 2026.
- **What an acceptance certificate should say** – the page a person reads, and the record behind it.
  17 November 2026.
- **The job ran, succeeded, and wrote nothing** – a detection engine that reports what it did not check.
  1 December 2026.

### Tools

The five tools in the chain, released on PyPI under Apache-2.0:
[`bmc-sensor-audit`](https://pypi.org/project/bmc-sensor-audit/),
[`presence-audit`](https://pypi.org/project/presence-audit/),
[`odm-cert-generator`](https://pypi.org/project/odm-cert-generator/),
[`fleet-sensor-baseline`](https://pypi.org/project/fleet-sensor-baseline/) and
[`arbiter-engine`](https://pypi.org/project/arbiter-engine/), the detection engine that `bmc-sensor-audit` and
`factory-line-audit` call directly; `fleet-sensor-baseline` aggregates `bmc-sensor-audit`'s output and never calls it.

## What is not here

The engine judges what it is handed: it has no opinion about what exists in the world and will not invent a fact to
fill a gap. It never acts. It ships no forecasting model of any domain, and the curated domain models are not
published; the mechanism is the contribution, the models are the accumulated work. Where a model declares no number,
the engine's calibration constants are its own, and every number it projects rests on approximations it made, each
stamped so a reader knows which to distrust. Every bridge above is by this author rather than an independent adopter,
and the moved line has no hardware exhibit yet: an absence under emulation is a fact about the emulator. The most
useful thing to send is a case where a tool reported a clean pass over something it did not evaluate; that is the
failure this work exists to prevent.
