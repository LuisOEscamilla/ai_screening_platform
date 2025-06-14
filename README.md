# Created by Luis Escamilla 
# AI-Driven Candidate Screening Platform

## Overview
An MVP that automates:
1. Resume upload (PDF/Word)  
2. NLP parsing into structured JSON  
3. ML-powered “fit” scoring  
4. Interactive React/D3 dashboard  
5. Real-time collaboration via WebSockets  

## Done Criteria
| Feature                 | Done When…                                                                                                         |
|-------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Resume Upload**       | • `POST /upload` returns `{ id: string, url: string }` in < 1 s for valid PDFs.<br>• Invalid file types return HTTP 400. |
| **Resume Parsing**      | • JSON output includes `name`, `email`, `skills[]`, `experience[]` for ≥ 90% of a 20-resume test set.<br>• Parses in < 2 s. |
| **Candidate Scoring**   | • Scores are numbers 0–100.<br>• Inference time < 200 ms per resume.<br>• Unit tests cover input/output types. |
| **Interactive Dashboard** | • Table shows candidate IDs & scores.<br>• Filter by score range & skill tag.<br>• Loads in < 1.5 s. |
| **Real-Time Collaboration** | • `new_resume` WebSocket event broadcasts to clients on parse.<br>• Clients display a toast in < 500 ms.<br>• Integration test verifies multi-client updates. |

## Success Metrics
| Metric               | Target         | Measurement Method                              |
|----------------------|----------------|-------------------------------------------------|
| Upload Latency       | < 1 s (p95)    | Timestamp logs in backend                       |
| Parse Accuracy       | ≥ 90% fields   | Nightly job vs. annotated gold-standard set     |
| Inference Time       | < 200 ms mean  | Timer around `model.predict()`                  |

## Prerequisites
- macOS with Homebrew  
- Python 3.10+  
- Node.js 16+ (via nvm)  
- Docker & Docker Compose  
- VS Code with recommended extensions  

## Getting Started

1. **Clone repository**  
   ```bash
   git clone git@github.com:<you>/ai-screening-platform.git
   cd ai-screening-platform
