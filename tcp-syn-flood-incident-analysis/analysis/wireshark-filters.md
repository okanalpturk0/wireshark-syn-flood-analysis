# Wireshark Display Filters

Use these **display filters** with an original `.pcap` or `.pcapng` capture. They do not open or filter an Excel workbook.

| Investigation goal | Display filter |
|---|---|
| TCP SYN packets without ACK | `tcp.flags.syn == 1 && tcp.flags.ack == 0` |
| Traffic to HTTPS port 443 | `tcp.dstport == 443` |
| Traffic involving the example server | `ip.addr == 192.0.2.1` |
| TCP reset packets | `tcp.flags.reset == 1` |
| HTTP requests (unencrypted HTTP) | `http.request` |
| HTTP POST requests | `http.request.method == "POST"` |
| HTTP error responses | `http.response.code >= 400` |

## How to use

1. Open the original capture in Wireshark.
2. Paste one filter into the **Display Filter** bar.
3. Press Enter.
4. Save screenshots only after removing unrelated sensitive information.

## Interpretation cautions

A high count of SYN packets can be suspicious, but a filter result alone does not prove a SYN flood. Compare rates over time, handshake completion, destination services, server metrics, and legitimate traffic patterns. HTTPS application data is encrypted; the `http` filters generally do not expose HTTPS requests unless traffic is decrypted or otherwise decoded.
