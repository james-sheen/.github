## Absent is not healthy

A server's baseboard management controller reports its sensors, and a reader that waits for a reading to cross a
line learns nothing from a sensor that reports nothing: silence reads as health. The report checks what a board's
configuration declares against what its firmware reports – on OpenBMC's public configuration corpus and on
upstream firmware – and follows the result into the documents a factory hands a buyer.

**The report**, version 1.0, CC BY 4.0: [DOI 10.5281/zenodo.23585862](https://doi.org/10.5281/zenodo.23585862) ·
[its source, claims ledger and case studies](https://github.com/james-sheen/absent-is-not-healthy)

**Upstream**: the two contradictory thresholds it found, filed as
[`entity-manager` issue #38](https://github.com/openbmc/entity-manager/issues/38).

### Posts

*Not yet published. Each is listed with the day it goes out, and becomes a link that day.*

- **Absent is not healthy** – what OpenBMC's configuration corpus declares, and what upstream firmware reports.
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
[`arbiter-engine`](https://pypi.org/project/arbiter-engine/), the detection engine underneath.
