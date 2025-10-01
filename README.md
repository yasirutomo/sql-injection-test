# sql-injection-test
Set of SQL Injection query for penetration testing

## About
This repository contains a curated set of SQL injection payloads organized by attack technique. The payloads are intended for authorized security testing, training, and research only — do not use them against systems without explicit permission.

## What’s in the payload file
The file Payload SQL Injection.txt contains grouped example payloads for five widely-used SQL injection techniques:
- Tautology / Boolean-based — payloads that turn a conditional into a tautology (e.g., OR 1=1) so that queries always evaluate true and return data. These are commonly used to bypass authentication checks or force broader results.
- Union-based (In-band: UNION) — payloads using the UNION operator to append attacker-controlled SELECT results to the application's query output; useful when the application returns database query results directly.
- Error-based (In-band: error disclosure) — payloads that deliberately cause database errors (or use functions that echo data in error messages) so the attacker can extract information from verbose DB error outputs.
- Blind SQL (Boolean-based blind) — payloads that do not return results directly but change the application behavior depending on true/false conditions. Attackers infer data by observing differences in responses
- Time-based (Inferential blind / time delay) — payloads that use time delays (e.g., SLEEP() or WAITFOR) to infer data when the application does not return query results or error messages. The attacker measures response times to extract bits of information.

> Note: these five categories are a concise grouping commonly used in testing and literature; they correspond to well-known classifications such as In-band (UNION, Error), Inferential/Blind (Boolean, Time), and other variants. See the review paper referenced below for a thorough taxonomy (https://doi.org/10.1007/978-981-16-8059-5_35).
