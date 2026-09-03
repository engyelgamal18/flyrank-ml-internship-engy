# Capstone Report — CTR / Engagement Opportunity Scoring

- **Author:** Engy Elgamal
- **Lane:**  CTR / Engagement Opportunity Scoring
- **Repo:**  https://github.com/engyelgamal18/flyrank-ml-internship-engy
- **Date:** September 2026

> Copy this file to `work/capstone_report.md` and fill it in as you build. Sections 1–8
> mirror the Pass / Needs-Work rubric axes, so nothing here is optional. Sections 0 and 9
> are **paper sections**: your deployed research paper must carry both, and they're here so
> you never rebuild them from memory at ship time.

## 0. Abstract

Five sentences, written last, placed first: question → data → method → headline result →
what the output is for. This is the top of your deployed paper.

## 1. Problem framing

The goal of this project is to find pages that may need a CTR review. The unit of analysis is a content page, and the output is a priority ranking. This ranking can help an editor decide which pages to review first. A wrong ranking could give priority to a page that does not really need review. Using search data helps compare many pages in a consistent way.

## 2. Data safety

I used search performance data such as impressions, clicks, CTR and average position. I did not use client names, URLs or private search queries. Content IDs were only used to identify pages and were not used as features. I also avoided fields such as trend direction and trend pct to reduce the risk of data leakage. No client identifying information is included in the work.

## 3. Baseline
The Week 4 baseline ranked pages using impressions and the gap between expected CTR and actual CTR. Pages with many impressions and lower than expected CTR received a higher score. This was a fair baseline because it used the same search data and the same validation period as the Week 5 ranking method. The baseline gave each page a score and a rank that could be compared with the new ranking.

## 4. Model / analysis

I used a ranking analysis because my goal is to find pages that may need review. I used impressions, CTR, and average search position to create a priority score. I did not use client information or private data. The priority score is used to rank pages for review.


## 5. Evaluation

I used a time-aware split. Earlier March data was used first, and the last week of March was used for validation. I compared the new ranking with the Week 4 baseline using the same validation data. The new ranking changed the priority of many pages, especially pages that had a low baseline score.

## 6. Interpretation

The new ranking found some pages that the baseline did not give high priority. Using CTR and average search position changed the ranking of many pages. This shows that using more than one search signal can help find different pages for review.

## 7. Recommendation

The ranking can help editors decide which pages to review first. Pages with higher priority scores can be checked for possible improvements. The ranking is a decision-support tool and should not be used as a final decision.

## 8. Reproducibility

The project can be reproduced from the public GitHub repository.

```bash
git clone https://github.com/engyelgamal18/flyrank-ml-internship-engy.git
cd flyrank-ml-internship-engy
pip install -r requirements.txt
```
The notebooks can be run from work/notebooks/. The FlyRank dataset requires a Hugging Face read token saved as HF_TOKEN. I did not use a random seed because this project uses ranking analysis and does not train a random model. I did not use a sealed holdout test.

## 9. Acknowledgments & data credit

Built on the [FlyRank ML Internship dataset](https://flyrank.ai/]
---

> **Claims checklist before submitting:** observed / measured / directional / decision-support
> **Metrics vs. base rate:** report your task's base rate (majority-class %) next to any
> precision@K or accuracy — a high score can just be a high base rate. AUC / lift over
> baseline are the honest discrimination numbers.
> language everywhere · no causal claims without an experiment or causal design · no
> "predicted Google's algorithm" · no client-identifying details · numbers in this report
> match a fresh re-run.
