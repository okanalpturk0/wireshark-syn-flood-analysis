# Wireshark Analysis: Suspected TCP SYN Flood

## Overview

This project analyzes an educational packet-log excerpt to investigate a suspected TCP SYN flood and its potential impact on web service availability.

## Objectives

- Review TCP connection patterns using Wireshark-style packet fields.
- Apply display filters to isolate suspicious SYN traffic.
- Document service-related errors observed in the supplied log.
- Recommend defensive measures and identify limitations in the evidence.

## Key Findings

- Repeated TCP SYN requests appear from a displayed source address.
- The supplied excerpt includes TCP reset responses and an HTTP `504 Gateway Time-out` entry.
- The observed pattern is consistent with a suspected SYN flood, but the excerpt alone does not prove resource exhaustion or establish the attacker's identity.

## Repository Structure

- `reports/` — Final incident report.
- `evidence/` — Packet-log and Wireshark evidence screenshots.
- `filters.md` — Display filters and their purposes.

## Tools

- Wireshark concepts and display filters
- TCP/IP packet analysis
- Incident reporting

## Limitations

This is an educational case study based on a supplied packet-log excerpt. It is not a live incident investigation. The displayed IP addresses are from documentation ranges, and actual financial losses or server resource utilization were not measured.

## Defensive Recommendations

- Enable appropriate SYN flood protection.
- Monitor incomplete TCP connections and server resource utilization.
- Consider rate limiting and upstream traffic filtering.
- Validate service availability after mitigation.

## Disclaimer

This project is for educational and portfolio purposes only.
