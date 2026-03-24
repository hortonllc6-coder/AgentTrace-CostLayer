# CostTrace: Cost Intelligence Layer for AI Agents

![Python](https://img.shields.io/badge/python-3.8+-blue) ![License: MIT](https://img.shields.io/badge/License-MIT-green)

---

## Overview

AgentTrace identified where AI agents fail. CostTrace is the continuation of this project.

Token counts are a technical metric. Dollar cost per execution step is a business metric. CostTrace bridges that gap by reading AgentTrace simulation logs and surfacing the real financial footprint of every agent decision, broken down by persona type, failure mode, and workflow stage.

This is Phase 3 of the AgentTrace infrastructure roadmap.

---

## The Problem

Most AI cost monitoring stops at the billing dashboard. You see a monthly total and nothing else. That tells you what you spent. It does not tell you where you bled.

When AgentTrace stress tested 100 execution steps across four distinct user personas, it found a 10% reliability drop on impatient persona queries. What that report did not answer was whether that failure mode also represented a disproportionate share of total spend. Longer retry loops, more tokens, more cost. CostTrace was built to find out.

---

## What CostTrace Does

CostTrace takes the raw token log output from an AgentTrace simulation and produces three outputs:

A cost-per-execution-step breakdown that assigns a dollar value to every interaction in the log using published model pricing rates.

A persona cost comparison that surfaces which user types drive the highest average spend per successful response and which failure modes are the most expensive to recover from.

A cumulative spend dashboard that visualizes total cost across all execution steps and identifies the inflection points where spend accelerates.

---

## Key Finding

*This section will be updated with live data once the simulation is run.*

Hypothesis: impatient persona queries are expected to show a higher cost-per-successful-response than formal or friendly personas due to increased retry loops triggered by compressed prompt inputs. If confirmed, this reframes the 10% reliability gap from a quality problem to a compounding cost risk at scale.

---

## How to Run It

**Option 1: Google Colab**
Open the notebook in the notebooks folder and run all cells. Your AgentTrace CSV log is the only required input.

**Option 2: Local Python**

```bash
pip install pandas matplotlib
python cost_trace.py --input data/agenttrace_simulation_logs.csv
```

The output dashboard image will save automatically to the outputs folder.

---

## File Structure

```
CostTrace/
├── README.md
├── cost_trace.py
├── data/
│   └── agenttrace_simulation_logs.csv
├── outputs/
│   └── cost_dashboard.png
└── notebooks/
    └── CostTrace_Colab.ipynb
```

---

## Roadmap Connection

CostTrace is Phase 3 of the AgentTrace infrastructure stack.

| Phase | Project | Status |
|:---|:---|:---|
| Phase 1 | AgentTrace: Execution Step Tracing | Complete |
| Phase 2 | LLM-as-a-Judge Audit Layer | Complete |
| Phase 3 | CostTrace: Cost Intelligence Layer | In Progress |
| Phase 4 | PostgreSQL Drift Analysis | Planned |

---

## Author

**Sydney A. Horton**
- **Role:** AI Strategist and Infrastructure Builder
- **Location:** Atlanta, GA
- **Focus:** Building the supervision, audit, and cost intelligence layer for production AI Agent workforces.
- **GitHub:** [hortonllc6-coder](https://github.com/hortonllc6-coder)

---

## License

Distributed under the MIT License. See LICENSE for more information.
