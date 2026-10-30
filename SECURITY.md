# Security Policy

## Supported releases

| Release | Window |
| --- | --- |
| 2.3 (current) | Full support |
| previous minor | Security fixes only |
| anything older | Upgrade first, then report |

Reports against unsupported builds are still read, and often still fixed, but
they queue behind the current line.

## How to report

Prefer the **Report a vulnerability** button on the Security tab. It keeps the
discussion private and links the report to the code at the exact commit.

Include:

- What the terminal showed, and what the venue actually did
- The workspace you were in (scanner, vault, orders, endpoints)
- Whether any vault was imported during the session

## Data handling commitments

- No telemetry, no crash reporting, no outbound request that is not a quote
  poll you asked for.
- Imported vault material stays in memory and in the local state file; the
  app never attaches it to a network request.
- Exports (CSV) contain exactly what is on screen, nothing derived.

If a report shows any of the above to be false, it is treated as critical
regardless of exploitability.

## Severity ladder

| Level | Example |
| --- | --- |
| Critical | Vault material leaves the machine, or code execution |
| High | A crafted quote response crashes the app and corrupts state |
| Medium | State file corruption on abnormal exit |
| Low | Anything cosmetic that leaks information on screen |

## After the fix

Advisories are published with the release that closes them, including a short
technical write-up. Reporters get a heads-up at least a day before public
disclosure.
