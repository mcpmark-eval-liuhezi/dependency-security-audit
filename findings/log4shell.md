# Log4Shell (CVE-2021-44228)

This document records the GitHub Security Advisory details for the Log4Shell
vulnerability, pulled from GitHub's advisory database.

## Advisory Facts

| Field | Value |
| --- | --- |
| GHSA identifier | `GHSA-jfh8-c2jp-5v3q` |
| CVE | `CVE-2021-44228` |
| Severity | **Critical** (CVSS 3.1 score: 10.0 — `CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H/E:H`) |
| Affected package | `org.apache.logging.log4j:log4j-core` |
| Ecosystem | Maven (Java) |
| Advisory title | Remote code injection in Log4j |
| Advisory URL | https://github.com/advisories/GHSA-jfh8-c2jp-5v3q |
| Published | 2021-12-10 |

## Plain-Language Summary

Log4Shell lets an attacker run **arbitrary code** on a server that runs a
vulnerable version of Log4j. Log4j versions prior to 2.16.0 did not protect
against attacker-controlled LDAP and other JNDI-related endpoints. If an
application logs any text an attacker can influence — such as input sent in
HTTP headers, usernames, error messages, or exception traces — the attacker can
craft a special log message that triggers Log4j to fetch and load malicious
code from a remote server they control. The result is remote code execution
(RCE) on the affected application, without needing to authenticate first.

## Affected Versions

- Any Log4j version prior to 2.15.0 is affected.
- Version 2.15.0 contained an earlier fix, but did not disable
  attacker-controlled JNDI lookups in all situations.
- From Log4j 2.16.0, JNDI lookups are disabled by default and message lookup
  substitution is removed.
- Security backports of the fix: 2.3.1, 2.12.2, and 2.12.3.

Only the `org.apache.logging.log4j:log4j-core` package is directly affected.
If in use, `org.apache.logging.log4j:log4j-api` should be kept at the same
version as `log4j-core`.

## Remediation

- Upgrade `log4j-core` to 2.16.0 or later (or a backport: 2.3.1, 2.12.2, 2.12.3).
- Log4j v1 is End Of Life (EOL) and will not receive patches for this issue;
  migrate to Log4j 2.16.0 where possible.
- If upgrading is not immediately possible, ensure no attacker-controlled JNDI
  lookups can resolve and that the `JndiLookup` class is not loaded.

## References

- GitHub Advisory Database: https://github.com/advisories/GHSA-jfh8-c2jp-5v3q
- NVD: https://nvd.nist.gov/vuln/detail/CVE-2021-44228
- Apache Log4j Security Guide: https://logging.apache.org/log4j/2.x/security.html
- Related advisory (CVE-2021-45046): https://github.com/advisories/GHSA-7rjr-3q55-vv33
