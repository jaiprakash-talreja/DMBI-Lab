# CA3 Content Beyond Syllabus

**High-Utility Itemset Mining: When the Most Frequent Pattern Is Not the Most Valuable One**

VESIT D15A Group 09 — Jaiprakash Talreja (54), Adarsh Singh (52), Vidushi Singh (53), Piyush Shukla (49)

- **Presentation:** [`PPT/CA3 DMBI Group 09.pptx`](<PPT/CA3 DMBI Group 09.pptx>) ([PDF](<PPT/CA3 DMBI Group 09.pdf>))
- **Demo notebook:** [`POC/DMBI_CA3_HUI_Demo.ipynb`](POC/DMBI_CA3_HUI_Demo.ipynb), with [`figures/`](POC/figures) and [`results/`](POC/results)

Apriori (Module V) counts how often items appear together. High-utility itemset mining also measures what those items are worth. The demo implements HUI-Miner with the FHM pair check and an FHM+ length limit, verifies it against exhaustive search on 300 random databases, and runs it on UCI Online Retail.

- The top 20 itemsets by support and by utility share only 2 itemsets.
- The top 20 by utility hold 1.65× the revenue of the top 20 by support.
- 77.6% of high-utility itemsets fall below 1% support, so Apriori at that setting misses them.

**Main reference:** Gan, W., Lin, J. C.-W., Fournier-Viger, P., Chao, H.-C., Tseng, V. S. and Yu, P. S. (2021). A Survey of Utility-Oriented Pattern Mining. *IEEE TKDE*, 33(4), 1306–1327. https://doi.org/10.1109/TKDE.2019.2942594

**Data:** *Online Retail* (2015), UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33
