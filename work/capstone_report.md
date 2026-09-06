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

This project studies how search performance signals can help identify content pages that may need review. I used March 2026 search performance data and evaluated the ranking on the validation period from March 25 to March 31. I created a priority ranking using impressions, CTR and average search position, and compared it with the Week 4 baseline on the same validation period. The new ranking changed the priority of several pages, showing that combining multiple search signals can identify different review opportunities than the baseline. The final ranking is intended as a decision-support tool to help editors decide which pages to review first.

## 1. Problem framing

The goal of this project is to find pages that may need a CTR review. The unit of analysis is a content page, and the output is a priority ranking. This ranking can help an editor decide which pages to review first. A wrong ranking could give priority to a page that does not really need review. Using search data helps compare many pages in a consistent way.

## 2. Data safety

I used search performance data such as impressions, clicks, CTR and average position. I did not use client names, URLs or private search queries. Content IDs were only used to identify pages and were not used as features. I also avoided fields such as trend direction and trend pct to reduce the risk of data leakage. No client identifying information is included in the work.

## 3. Baseline
The Week 4 baseline ranked pages using impressions and the gap between expected CTR and actual CTR. Pages with many impressions and lower than expected CTR received a higher score. This was a fair baseline because it used the same search data and the same validation period as the Week 5 ranking method. The baseline gave each page a score and a rank that could be compared with the new ranking.

## 4. Model / analysis

I used a ranking analysis because my goal is to find pages that may need review. I used impressions, CTR, and average search position to create a priority score. I did not use client information or private data. I used a time-aware split, with March 1–24 as the earlier period and March 25–31 for validation. The priority score is used to rank pages for review.

## 5. Evaluation

I used a time-aware split. Data from March 1 to March 24 was used as the earlier period and March 25 to March 31 was used for validation. I compared the new ranking with the Week 4 baseline using the same validation data. The new ranking changed the priority of many pages, especially pages that had a low baseline score.

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
The notebooks can be run from the work/notebooks/ folder. The FlyRank dataset requires a Hugging Face read token saved as HF_TOKEN. This project uses ranking analysis and does not train a random model, so I did not use a random seed. I did not use a sealed holdout test.

## 9. Acknowledgments & data credit

Built on the [FlyRank ML Internship dataset](https://flyrank.ai/)
---


