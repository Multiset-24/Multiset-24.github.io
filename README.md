# System Design — HLD + LLD (Hinglish)

SDE-1 / SDE-2 interviews ke liye system design notes, Hinglish me (Hindi in Roman script + English technical terms). Payments domain (UPI, wallet, gateway, ledger, recon) pe focus hai, kyunki examples wahi se aaye hain.

**Website:** https://multiset-24.github.io (search, sidebar aur rendered diagrams ke saath)

**78 docs**, 2630 KB markdown. Export date: 2026-10-17.

## Har lesson ka format

Sab lessons ek hi structure follow karte hain, taaki padhna predictable rahe:

| Section | Kya hota hai |
| --- | --- |
| Opening paragraph | Pehli line me hi definition — ye cheez kya hai |
| Ye cheez hai kya | Kis category ki cheez hai, kis problem ke liye, lesson ke baad kya kar paoge |
| Sawaal | Ek concrete payments scenario — pehle khud 5 min socho |
| Problem kyun aata hai | Root causes, bullets me |
| Naive approach | Pehla obvious solution aur woh exactly kahan tootta hai |
| Sahi design | Step-by-step, mermaid diagram ya chalne layak Java code ke saath |
| Kya choose karein aur kyun | Option / Kab use karo / Kab mat karo table |
| India me kaise hota hai | Paytm, PhonePe, Razorpay, UPI, NPCI, RBI ke real cited links |
| Interview follow-ups | Jo sawaal aage poochha jaata hai, chhote jawab ke saath |
| Self-check | Recall sawaal, bina dekhe |
| Notebook | 4–6 compact lines, revision ke liye |
| Deep Dive (SDE-2) | Jab time ho — extra depth |

## Padhne ka order

1. **HLD Part 0 · Base Camp** — framework, estimation, networking, API design
2. **HLD 1A–1F** — scaling, cache, DB, sharding, Kafka, ops
3. **LLD 1A–1B** — OOP aur SOLID (parallel me chalao)
4. **HLD 2A–2G** — payments ke patterns: idempotency, ledger, saga, locks, resilience, recon, security
5. **LLD 2A–2C + Part 3** — design patterns aur concurrency
6. **Case studies** — C1–C14 (HLD) aur D1–D24 (LLD machine coding)
7. **Q1–Q19** — classic interview questions

## HLD — Zones (core concepts)

Part 0 se 2G tak. Har zone doc me us zone ke saare lessons hain — definition, Sawaal, naive approach, sahi design, trade-off table, India context, interview follow-ups, self-check, notebook.

| # | Doc | File |
| --- | --- | --- |
| 1 | HLD Part 0 — Base Camp | [`00-part0-base-camp.md`](hld/zones/00-part0-base-camp.md) |
| 2 | 1A · Scaling Valley | [`01a-scaling-valley.md`](hld/zones/01a-scaling-valley.md) |
| 3 | 1B · Cache Caves | [`01b-cache-caves.md`](hld/zones/01b-cache-caves.md) |
| 4 | 1C · DB Dungeon | [`01c-db-dungeon.md`](hld/zones/01c-db-dungeon.md) |
| 5 | 1D · Shard Mountains | [`01d-shard-mountains.md`](hld/zones/01d-shard-mountains.md) |
| 6 | 1E · Kafka River | [`01e-kafka-river.md`](hld/zones/01e-kafka-river.md) |
| 7 | 1F · Ops Tower | [`01f-ops-tower.md`](hld/zones/01f-ops-tower.md) |
| 8 | 2A · Idempotency Island | [`02a-idempotency-island.md`](hld/zones/02a-idempotency-island.md) |
| 9 | 2B · Ledger Library | [`02b-ledger-library.md`](hld/zones/02b-ledger-library.md) |
| 10 | 2C · Saga Sea | [`02c-saga-sea.md`](hld/zones/02c-saga-sea.md) |
| 11 | 2D · Lock Fort | [`02d-lock-fort.md`](hld/zones/02d-lock-fort.md) |
| 12 | 2E · Resilience Ridge | [`02e-resilience-ridge.md`](hld/zones/02e-resilience-ridge.md) |
| 13 | 2F · Recon Ruins | [`02f-recon-ruins.md`](hld/zones/02f-recon-ruins.md) |
| 14 | 2G · Security Vault | [`02g-security-vault.md`](hld/zones/02g-security-vault.md) |

## HLD — Case studies (C1–C14)

Payments ke real systems ka end-to-end HLD. Boss level: pehle 45 min khud kaagaz pe design karo, phir doc padho.

| # | Doc | File |
| --- | --- | --- |
| 1 | C1 · UPI PSP app (PhonePe/Paytm) | [`c01.md`](hld/case-studies/c01.md) |
| 2 | C2 · Payment gateway (Razorpay) | [`c02.md`](hld/case-studies/c02.md) |
| 3 | C3 · Digital wallet | [`c03.md`](hld/case-studies/c03.md) |
| 4 | C4 · Ledger service | [`c04.md`](hld/case-studies/c04.md) |
| 5 | C5 · Reconciliation system | [`c05.md`](hld/case-studies/c05.md) |
| 6 | C6 · Refund system | [`c06.md`](hld/case-studies/c06.md) |
| 7 | C7 · Fraud detection engine | [`c07.md`](hld/case-studies/c07.md) |
| 8 | C8 · Notification service | [`c08.md`](hld/case-studies/c08.md) |
| 9 | C9 · Merchant settlement | [`c09.md`](hld/case-studies/c09.md) |
| 10 | C10 · Split bill / P2P | [`c10.md`](hld/case-studies/c10.md) |
| 11 | C11 · AutoPay / mandates | [`c11.md`](hld/case-studies/c11.md) |
| 12 | C12 · QR + Soundbox | [`c12.md`](hld/case-studies/c12.md) |
| 13 | C13 · Loyalty / cashback | [`c13.md`](hld/case-studies/c13.md) |
| 14 | C14 · Txn history at scale | [`c14.md`](hld/case-studies/c14.md) |

## HLD — Interview questions (Q1–Q19)

Classic system design interview questions, wahi format me.

| # | Doc | File |
| --- | --- | --- |
| 1 | Q1 · URL shortener | [`q01.md`](hld/questions/q01.md) |
| 2 | Q2 · Rate limiter | [`q02.md`](hld/questions/q02.md) |
| 3 | Q3 · WhatsApp | [`q03.md`](hld/questions/q03.md) |
| 4 | Q4 · News feed | [`q04.md`](hld/questions/q04.md) |
| 5 | Q5 · Uber / Ola | [`q05.md`](hld/questions/q05.md) |
| 6 | Q6 · Swiggy / Blinkit | [`q06.md`](hld/questions/q06.md) |
| 7 | Q7 · BookMyShow | [`q07.md`](hld/questions/q07.md) |
| 8 | Q8 · Distributed cache | [`q08.md`](hld/questions/q08.md) |
| 9 | Q9 · Notification system | [`q09.md`](hld/questions/q09.md) |
| 10 | Q10 · Search autocomplete | [`q10.md`](hld/questions/q10.md) |
| 11 | Q11 · YouTube / Netflix | [`q11.md`](hld/questions/q11.md) |
| 12 | Q12 · Google Drive | [`q12.md`](hld/questions/q12.md) |
| 13 | Q13 · Web crawler | [`q13.md`](hld/questions/q13.md) |
| 14 | Q14 · Snowflake ID generator | [`q14.md`](hld/questions/q14.md) |
| 15 | Q15 · Stock exchange | [`q15.md`](hld/questions/q15.md) |
| 16 | Q16 · IRCTC Tatkal | [`q16.md`](hld/questions/q16.md) |
| 17 | Q17 · Leaderboard | [`q17.md`](hld/questions/q17.md) |
| 18 | Q18 · Job scheduler | [`q18.md`](hld/questions/q18.md) |
| 19 | Q19 · Metrics system | [`q19.md`](hld/questions/q19.md) |

## LLD — Zones (OOP, SOLID, patterns, threads)

Java ka low level design: OOP Village se Thread Jungle tak. Har lesson me chalne layak Java code hai.

| # | Doc | File |
| --- | --- | --- |
| 1 | Part 0 · Base Camp | [`00-lld-part0-base-camp.md`](lld/zones/00-lld-part0-base-camp.md) |
| 2 | 1A · OOP Village | [`01a-oop-village.md`](lld/zones/01a-oop-village.md) |
| 3 | 1B · SOLID Temple | [`01b-solid-temple.md`](lld/zones/01b-solid-temple.md) |
| 4 | 2A · Creational Forge | [`02a-creational-forge.md`](lld/zones/02a-creational-forge.md) |
| 5 | 2B · Structural Bridge | [`02b-structural-bridge.md`](lld/zones/02b-structural-bridge.md) |
| 6 | 2C · Behavior Bazaar | [`02c-behavior-bazaar.md`](lld/zones/02c-behavior-bazaar.md) |
| 7 | Part 3 · Thread Jungle | [`03-thread-jungle.md`](lld/zones/03-thread-jungle.md) |

## LLD — Case studies (D1–D24)

Machine coding round ke problems — haath se code karne ke liye.

| # | Doc | File |
| --- | --- | --- |
| 1 | D1 · Payment gateway / UPI flow | [`d01.md`](lld/case-studies/d01.md) |
| 2 | D2 · Digital wallet | [`d02.md`](lld/case-studies/d02.md) |
| 3 | D3 · Splitwise | [`d03.md`](lld/case-studies/d03.md) |
| 4 | D4 · Parking lot | [`d04.md`](lld/case-studies/d04.md) |
| 5 | D5 · Elevator | [`d05.md`](lld/case-studies/d05.md) |
| 6 | D6 · BookMyShow | [`d06.md`](lld/case-studies/d06.md) |
| 7 | D7 · Vending machine | [`d07.md`](lld/case-studies/d07.md) |
| 8 | D8 · ATM | [`d08.md`](lld/case-studies/d08.md) |
| 9 | D9 · Rate limiter | [`d09.md`](lld/case-studies/d09.md) |
| 10 | D10 · LRU / LFU cache | [`d10.md`](lld/case-studies/d10.md) |
| 11 | D11 · Snake & Ladder | [`d11.md`](lld/case-studies/d11.md) |
| 12 | D12 · Tic-tac-toe | [`d12.md`](lld/case-studies/d12.md) |
| 13 | D13 · Chess | [`d13.md`](lld/case-studies/d13.md) |
| 14 | D14 · Logger framework | [`d14.md`](lld/case-studies/d14.md) |
| 15 | D15 · Notification service | [`d15.md`](lld/case-studies/d15.md) |
| 16 | D16 · Food delivery | [`d16.md`](lld/case-studies/d16.md) |
| 17 | D17 · Library management | [`d17.md`](lld/case-studies/d17.md) |
| 18 | D18 · Inventory management | [`d18.md`](lld/case-studies/d18.md) |
| 19 | D19 · Pub-sub / message queue | [`d19.md`](lld/case-studies/d19.md) |
| 20 | D20 · Task scheduler | [`d20.md`](lld/case-studies/d20.md) |
| 21 | D21 · Cab booking | [`d21.md`](lld/case-studies/d21.md) |
| 22 | D22 · Hotel booking | [`d22.md`](lld/case-studies/d22.md) |
| 23 | D23 · Stock broker | [`d23.md`](lld/case-studies/d23.md) |
| 24 | LLD D24 · Coupon / cashback engine | [`d24.md`](lld/case-studies/d24.md) |

## Notes

- Diagrams mermaid me hain — GitHub inhe markdown me seedha render karta hai.
- Java snippets chalne layak hain; `main` ka output comments me likha hai.
- Byline me jo date chip tha woh export me plain text ban gaya hai — content pe koi asar nahi.
- Source: Claude Docs se markdown export, structure waisa hi rakha gaya hai.
