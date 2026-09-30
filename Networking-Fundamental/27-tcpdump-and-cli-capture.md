# 27 — tcpdump and CLI Capture

## Start simple

```bash
sudo tcpdump -i any
```

## Useful filters

```bash
sudo tcpdump -i eth0 host 10.0.0.5
sudo tcpdump -i eth0 port 53
sudo tcpdump -i eth0 tcp
sudo tcpdump -i eth0 icmp
```

## Save a capture

```bash
sudo tcpdump -i eth0 -w capture.pcap
```

Then inspect it in Wireshark.

## Read a capture

```bash
tcpdump -nn -r capture.pcap
```

## Why CLI capture matters

During incidents you may not have a GUI.

You should be able to:

- capture
- filter
- save
- extract evidence
- transfer the capture
- inspect it later

## Challenge

Capture a DNS lookup and answer:

```text
Who asked?
Which resolver?
What name?
What record?
How long?
What response?
```
