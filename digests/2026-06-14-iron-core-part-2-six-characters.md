---
date: 2026-06-14
url: https://ajitem.com/blog/iron-core-part-2-six-characters/
tags: [engineering, product]
rating: 4
---

## [Iron Core Part 2: Six Characters](https://ajitem.com/blog/iron-core-part-2-six-characters/)

**Summary**
This article is the second part of a series that reverse-engineers the data systems behind commercial aviation by examining an actual airline booking record (called a PNR, or Passenger Name Record) field by field. A PNR is not a conventional database row — it is an append-only document, similar to a log file, that accumulates every change made to a booking over time. The author reveals that the six-character booking reference you receive by email is not a globally unique identifier: two different passengers on two different booking systems can share the same code. The only truly stable, globally unique identifier is the e-ticket number — a 13-digit code that persists even when a flight is cancelled and rebooked entirely. The article also explains how airline fares are calculated in a currency-neutral intermediate unit (the NUC, or Neutral Unit of Construction) so that prices can be set at the route level and only converted to local currency at the moment of purchase.

**Key takeaways**
- The e-ticket number (not the PNR booking code) is the real primary key — it survives re-accommodations and re-bookings where the PNR itself may be replaced; always store it when building travel integrations.
- IATA fares price at the city level, not the airport level: "LON" covers Heathrow, Gatwick, Stansted, and City Airport as a single fare destination, so a passenger can fly into one London airport and depart from another without a fare penalty.
- The NUC (Neutral Unit of Construction) is a currency-neutral pricing layer: fares are published in NUCs, and the exchange rate is applied only once at the time of ticketing — the same pattern is worth borrowing in any multi-currency system where price consistency across rate fluctuations matters.

**Importance** ★★★★☆ (4/5)
*Rare, well-sourced deep-dive into a 60-year-old system that still moves billions of passengers — the identifier hierarchy and NUC patterns are directly applicable to anyone building on travel APIs.*
