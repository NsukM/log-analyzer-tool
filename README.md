# Log Analyzer Tool (Java)

A lightweight Java utility designed to parse, aggregate, and report on application logs. I built this to simulate the incident investigation workflows used in backend systems—essentially turning raw log data into a readable post-mortem summary.

---

## What it does

When pointed at a log file, the tool handles the heavy lifting of:
* **Parsing:** Breaking down raw strings into structured data (Level, Service, Message).
* **Counting:** Getting a high-level view of `INFO`, `WARN`, and `ERROR` counts.
* **Aggregation:** Identifying which services are failing most often and surfacing the most frequent error messages.
* **Resilience:** It’s built to skip malformed lines rather than crashing, which is critical for real-world logs.

## Why I built this

Logs are the first thing you look at during a "sev-1" production issue. I wanted to build a tool that forced me to think about:
1.  **Data Extraction:** Handling string manipulation and regex without relying on heavy external libraries.
2.  **State Management:** Using the right Java Collections (like `HashMap` and `TreeMap`) to keep the analysis efficient.
3.  **Readability:** Producing an output that an engineer can actually use to diagnose a system in under 10 seconds.

## Sample Input Format

The analyzer expects a standard log format, though it's flexible with spacing:
`2026-02-10T14:30:00Z ERROR PaymentService - Connection refused requestId=8821`

---

## Getting Started

### Prerequisites
* JDK 11 or higher

### Usage
Compile the source and run it against your target log file:

```bash
javac src/LogAnalyzer.java
java -cp src LogAnalyzer path/to/your/app.log
