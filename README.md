TCP SYN Flood Incident Analysis
Project type: Educational cybersecurity case study
Focus areas: Network security · Incident analysis · TCP/IP · Wireshark · DoS mitigation

Overview
This project analyzes an educational TCP/HTTP traffic log in the context of a travel-agency website experiencing connection timeouts. The observed repeated TCP SYN requests are consistent with a TCP SYN flood / denial-of-service (DoS) hypothesis.

Evidence note: This is an analysis of a supplied educational spreadsheet, not a live incident investigation. The spreadsheet is a summarized log, not a raw PCAP/PCAPNG capture. Findings are indicative and should not be presented as proof of a real-world attacker or outage.

Key observations
The supplied TCP log contains 174 records across approximately 48.68 seconds.
The example source address 203.0.113.0 appears in 140 records.
Repeated SYN traffic is directed toward the example server address 192.0.2.1 on destination port 443.
The pattern is consistent with repeated TCP connection initiation and possible connection-establishment disruption.
The log alone does not establish attacker identity, intent, actual server resource exhaustion, or financial loss.
The IP addresses in this case study are from documentation/example ranges and should not be attributed to real infrastructure.

Incident classification
Suspected technique: TCP SYN flood
Likely impact in the scenario: Denial of service (DoS), causing slow responses, failed connections, and HTTP(S) service timeouts.

A DoS attack may originate from one source or a limited set of sources. A DDoS attack uses multiple distributed sources. The provided spreadsheet alone does not establish a distributed attack.

Recommended response
Preserve logs and document the timeline.
Correlate the spreadsheet with server, firewall, load-balancer, and monitoring telemetry.
Consider upstream DDoS protection, SYN proxy/SYN cookies, and rate limiting supported by the environment.
Do not rely solely on blocking one source IP; addresses can change or be spoofed.
Monitor SYN rates, incomplete handshakes, connection backlog, latency, error rates, and server resource use.
Record remediation steps and validate recovery.
Repository contents
reports/incident-report.pdf — shareable report
reports/incident-report.docx — editable report
analysis/wireshark-filters.md — display filters and their purpose
evidence/figures/traffic-summary.png — record-count visualization
Wireshark filters
Filters are useful only when a real packet capture (.pcap or .pcapng) is available. The Excel spreadsheet cannot be opened as packet data in Wireshark.

Methodology and limitations
This is a portfolio learning exercise based on a provided course dataset. Packet-level conclusions should be verified against an original capture and supporting infrastructure logs before being treated as a confirmed incident. Record counts are spreadsheet rows, not necessarily a validated packet-rate measurement.

Skills demonstrated
TCP handshake and SYN-flood concepts
Network traffic pattern interpretation
Incident classification and impact assessment
Defensive mitigation planning
Technical reporting and evidence limitations
Attribution
Educational exercise inspired by a network-security course scenario. The supplied dataset and course materials should be credited according to the course's reuse terms.
