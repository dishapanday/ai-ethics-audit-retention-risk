# AI Ethics Audit: Workplace "Retention Risk" Scoring System

A responsible-AI audit of **Zenith-Mind**, a fictional AI system that gives warehouse workers a 0–100 "Retention Risk Score". The system was introduced as a burnout and wellness tool, but leadership also wanted to use the scores for staffing decisions.

Course: MAI105 Ethics in Artificial Intelligence, Master of AI Design & Development, Seneca Polytechnic. Two-person case study, **graded 100/100**.

## What the audit covered

| Area | Key finding |
|---|---|
| **Technical audit** | Recall 0.80 (40/50) vs. precision 0.727 (40/55): the model caught most burned-out workers, but about 1 in 4 high-risk flags was a false positive. |
| **Fairness / proxies** | 13 of 15 false positives were single parents leaving at 5:00 p.m. for daycare, so signals like badge swipes and time-off-task can act as proxies for caregiving duties rather than burnout. |
| **Privacy** | Using a contextual-integrity analysis: combining snack purchases with wearable heart-rate data repurposes everyday workplace data and risks sensitive health inferences (e.g. pregnancy) that workers never shared. |
| **Accountability & governance** | Who is responsible when a manager cuts shifts based on an unverified score? |
| **System map** | End-to-end flow from data inputs to model, score, manager decision and harm, with the ethical hazard at each stage. |

## My contributions

I led the **accountability & governance** analysis and the **one-page system map**:

- **"Moral crumple zone" analysis:** showed how the manager who cut a pregnant worker's shifts absorbs blame for a failure that was also built upstream: the choice of features, naming the output a *Retention* Risk Score instead of a wellness indicator, and giving scores to managers at all. I argued for spreading accountability across the whole chain while still holding the manager responsible for acting on an uncertain prediction.
- **Bias-review RACI matrix:** a governance plan covering 9 activities (purpose definition, proxy-feature review, subgroup error analysis, release approvals, complaints and appeals) across the VP of Operations, lead data scientist, HR director and an external ethics auditor. It includes:
  - a **pre-release independent review** before every batch of scores reaches managers, not just a quarterly check;
  - an auditor-imposed **hold on releasing scores** that HR cannot override;
  - an **escalation route** to a board-level Audit & Ethics Committee if leadership pushes to release scores after a failed review.
- **System map:** traced how data inputs become a score, a managerial decision and real harm (lost income, privacy loss, discrimination), including a *predicted* feedback loop, clearly marked as unproven, where the consequences of decisions could feed back into future scores.

## Recommendations

- No PIPs, shift cuts or other staffing actions based **solely** on automated scores.
- A strict separation between wellness/health data and HR performance records.
- Independent subgroup error and proxy-feature review before any score reaches a manager.
- An appeal process for affected workers.

## Why it matters

A model with "good enough" metrics can still cause serious harm once its output is tied to employment decisions. Responsible AI means evaluating the **whole decision pipeline**, not just the model.

*Written summary of my coursework. The full graded report is not reproduced here.*
