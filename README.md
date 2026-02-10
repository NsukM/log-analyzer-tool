
---

# ✅ README for `log-analyzer-tool`

```md
# Log Analyzer Tool (Java)

This project is a small Java-based log analysis tool inspired by real-world
production debugging and incident investigation scenarios.

It simulates how engineers analyze application logs to identify error patterns,
service-level issues, and recurring failures in distributed systems.

---

## What the Tool Does

Given a log file, the analyzer:
- Parses log entries line by line
- Counts occurrences of INFO, WARN, and ERROR events
- Aggregates error messages by frequency
- Groups errors by service/component
- Produces a readable summary report in the console

---

## Motivation

While working with cloud-based and distributed systems, logs are often the first
and most important source of truth when diagnosing production issues.

This project was built to strengthen my understanding of:
- Log-driven debugging
- Data aggregation using core data structures
- Defensive parsing of imperfect input
- Writing maintainable, readable backend utilities

---

The tool is tolerant of minor formatting differences and safely ignores malformed
lines.

---

## Design Choices

- Uses standard Java collections (`Map`, `List`)
- Avoids external libraries to focus on fundamentals
- Separates parsing, aggregation, and reporting logic
- Favors clarity and robustness over over-optimization

---

## How to Run

```bash
javac src/LogAnalyzer.java
java -cp src LogAnalyzer logs/sample.log

## Example Log Format

