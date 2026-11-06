# Telegram Protocol: MTProto Architecture, Security and Trade-offs

A 19-slide presentation that explains how Telegram's custom protocol, **MTProto 2.0**, works and evaluates its security design.

| | |
|---|---|
| **Presented by** | Shayla Akter |
| **ID** | IT24022 |
| **Session** | 2023-24 |
| **Department** | Information and Communication Technology (ICT), Mawlana Bhashani Science and Technology University (MBSTU), Santosh, Tangail-1902 |
| **Supervised by** | Dr. Nazrul Islam, Associate Professor, Dept. of ICT, MBSTU |

## Overview

Telegram protects messages with its own protocol instead of a standard one like TLS. This presentation:

- explains the layers, key creation and message encryption of MTProto 2.0
- compares cloud chats with Secret Chats
- reviews published security analyses
- compares Telegram with WhatsApp and Signal
- gives practical recommendations for users

The study is a **literature-based review**. No new experiments or independent cryptanalysis were done.

## Files

| File | Description |
|---|---|
| `Telegram_Protocol_MBSTU_Detailed_Shayla_Akter.pptx` | Editable PowerPoint presentation |
| `Telegram_Protocol_MBSTU_Detailed_Shayla_Akter.pdf` | PDF version of the slides |
| `README.md` | This file |

## Slide Outline

| Slide | Title |
|---|---|
| 1 | Cover page |
| 2 | Presentation Outline |
| 3 | Introduction and Research Problem |
| 4 | Background: What Is Telegram? |
| 5 | Related Work and Research Gap |
| 6 | Methodology: MTProto 2.0 architecture |
| 7 | Methodology: Key Creation |
| 8 | Methodology: Message Encryption |
| 9 | Cloud Chats and Secret Chats |
| 10 | Analysis Setup |
| 11 | Results and Discussion |
| 12 | Security Properties of MTProto 2.0 |
| 13 | Published Security Analyses |
| 14 | Quantitative Comparison |
| 15 | Cryptographic Primitives Compared |
| 16 | Practical Recommendations |
| 17 | Conclusions and Future Work |
| 18 | Selected References |
| 19 | Thank You |

## Key Points

- **Architecture:** three layers: API query layer (TL-serialised RPC requests), cryptographic layer (AES-256-IGE, SHA-256 `msg_key`) and transport layer (TCP, HTTP or WebSocket).
- **Key creation:** a Diffie-Hellman exchange produces a shared 2048-bit `auth_key`, identified by a 64-bit `auth_key_id`.
- **Cloud chats (default):** encrypted from client to server only, so the server can read the content.
- **Secret Chats (opt-in):** end-to-end encrypted between two devices, one-to-one only.
- **Comparison:** WhatsApp and Signal use end-to-end encryption by default. Telegram cloud chats do not.
- **Takeaway:** flaws found in earlier analyses were fixed, and the main remaining concern is trust in the server.

## Research Gap

Formal proofs cover modified variants of the protocol, and default chats stay readable by the server.

## Future Work

Test MTProto traffic and Secret Chats in a controlled lab setup.

## References

1. J. B. Jakobsen and C. Orlandi, "On the CCA (in)security of MTProto," ACM SPSM Workshop, 2016.
2. M. Miculan and N. Vitacolonna, "Automated symbolic verification of Telegram's MTProto 2.0," 2021.
3. M. R. Albrecht, L. Mareková, K. G. Paterson and I. Stepanovs, "Four attacks and a proof for Telegram," IEEE S&P, 2022.
4. J. Sušánka and J. Kokes, "Security analysis of the Telegram IM," ROOTS, 2017.
5. Telegram, "MTProto Mobile Protocol," core.telegram.org/mtproto.
6. Telegram, "End-to-End Encryption, Secret Chats," core.telegram.org/api/end-to-end.

## How to Use

Open the `.pptx` in Microsoft PowerPoint (or LibreOffice Impress) to present or edit it. Use the `.pdf` for sharing or printing.
