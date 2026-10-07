# OSI Model

The seven OSI layers:

1. Physical
2. Data Link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

## Practical interpretation

| Layer | Main question | Examples |
|---|---|---|
| 7 | What does the application want? | HTTP, DNS, SSH |
| 6 | How is data represented? | encoding, TLS concepts |
| 5 | How is a communication session managed? | session concepts |
| 4 | How is end-to-end transport handled? | TCP, UDP |
| 3 | Which network should receive this? | IP, routing |
| 2 | How does this local link deliver it? | Ethernet, MAC |
| 1 | How are bits/signals transmitted? | copper, fiber, radio |

The OSI model is primarily a **thinking and troubleshooting framework**.

Do not force every real protocol into one perfect box.
