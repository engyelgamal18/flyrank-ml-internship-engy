# Capstone Report — CTR / Engagement Opportunity Scoring

- **Author:** Engy Elgamal
- **Lane:**  CTR / Engagement Opportunity Scoring
- **Repo:**  https://github.com/engyelgamal18/flyrank-ml-internship-engy
- **Date:** September 2026

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

The Week 4 baseline and the new ranking were compared using the same validation period: March 25–31, 2026. The new method changed the priority of many pages. For example, one page moved from baseline rank 136 to new rank 1. Another page moved from baseline rank 300 to new rank 9. Some pages with a baseline score of zero also moved to the top of the new ranking. This shows that the new method can find review opportunities that the baseline may miss. These results are directional. The ranking is a decision-support tool and does not prove that the new method is always better.

## 6. Interpretation

This analysis has some limitations. The priority ranking is based only on search performance signals such as impressions, CTR and average position. It does not include content quality, conversions or business value. A high priority score does not prove that changing a page will improve its CTR. The ranking should be used as a guide to help editors decide which pages to review first. The analysis is limited to March 2026 data, so the ranking should be reviewed again when newer data becomes available.

## 7. Recommendation

The highest-ranked pages should be reviewed first. These pages have a combination of high impressions, low CTR, and weaker average search position.
Editors can review the page title, metadata, and content to look for possible CTR improvements.
Pages that moved much higher in the new ranking than in the baseline should receive extra attention because the new method identified them as higher-priority review opportunities. These recommendations are a guide and not an automatic decision.

## 8. Reproducibility

The full project is available in the public GitHub repository:

https://github.com/engyelgamal18/flyrank-ml-internship-engy

The main capstone notebook is available at:

work/notebooks/capstone.ipynb

The supporting weekly notebooks are also available in the work/notebooks/ folder.

To reproduce the environment:

```bash
git clone https://github.com/engyelgamal18/flyrank-ml-internship-engy.git
cd flyrank-ml-internship-engy
pip install -r requirements.txt
```
The FlyRank dataset requires a Hugging Face read token saved as HF_TOKEN. This project uses ranking analysis and does not train a random model, so I did not use a random seed. I did not use a sealed holdout test.

## 9. Acknowledgments & data credit

Built on the [FlyRank ML Internship dataset](https://flyrank.ai/)
---


