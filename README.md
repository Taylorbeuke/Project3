# 70 Years of U.S. Economic Inequality

An interactive data story exploring how income distribution, the Gini coefficient, and housing affordability have shifted in the United States since the 1960s. Built with **Python (Altair + matplotlib)**, **ArcGIS StoryMaps**, and **Power BI**, then narrated through long-form writing on Medium.

<img width="832" height="473" alt="Screenshot 2026-05-06 at 4 36 32 PM" src="https://github.com/user-attachments/assets/bce1f3af-5ded-4e8e-9ddb-37b09ac1bc27" />

[![Gini Index Over Time, annotated with historical events](images/gini_index_annotated.png)](https://arcg.is/0ary0C1)

> *The Gini Index from 1963 to today, annotated with the policy and economic events that shaped it. Click the image to open the full interactive StoryMap.*

---

## Quick Links

| Deliverable | Link |
|---|---|
| **Medium article (redesign)** — *70 Years of U.S. Economic Inequality* | https://medium.com/@taylorbeuke/70-years-of-u-s-economic-inequality-a5f2c7d88cc3 |
| **Medium article (original designs)** — *The Myth of the American Dream* | https://medium.com/@taylorbeuke/the-myth-of-the-american-dream-c0965c96fb7d |
| **ArcGIS StoryMap (final dashboard)** | https://arcg.is/0ary0C1 |
| **Source data repo** | https://github.com/Taylorbeuke/Project3 |

> **Tip:** click the StoryMap link — it's the centerpiece of the project and where the visualizations live in their final, interactive form.

---

## The Story

Economic inequality in the U.S. is one of the most discussed and most contested topics in modern public discourse. The intuition that the top earners have pulled away from the rest is widely shared, but rarely shown side-by-side with the underlying data over a long enough time horizon to be convincing.

This project answers a simple question: **what does 65+ years of U.S. inequality data actually look like, and how has the buying power of the median American shifted relative to housing costs?**

The analysis focuses on three measures:

1. **Share of income by percentile** — how the income pie has been sliced over time
2. **The Gini coefficient** — a single-number measure of overall income inequality
3. **Median personal income vs. median housing prices** — buying power of a typical earner

The project began as a group effort (*The Myth of the American Dream*, April 2025) and was later rebuilt as a solo redesign with sharper storytelling, tighter interactions, and a more cohesive visual identity.

---

## Tools & Stack

| Tool | What it was used for |
|---|---|
| **Python — Altair** | Interactive charts (year-slider pie chart, linked-tooltip income graph, income-vs-housing chart). Charts were exported to standalone HTML and embedded into the StoryMap. |
| **Python — matplotlib** | Static visualizations and exploratory charts during the analysis phase. |
| **Python — pandas** | Cleaning and reshaping the World Bank and IPUMS datasets, joining percentile data with housing data, computing year-over-year change metrics. |
| **Power BI** | Additional dashboard view of inequality metrics, used for cross-platform comparison and to extend the storytelling beyond what was practical in Altair. |
| **ArcGIS StoryMaps** | The narrative wrapper — embeds the interactive Altair charts and walks readers through the story. |
| **Buffs Create** | Static hosting for the exported Altair HTML files so they could be embedded in StoryMaps. |
| **Medium** | Long-form write-ups of the design process, iterations, and final reflections. |

---

## Featured Visualizations

The four interactive/static visualizations that anchor the StoryMap:

**1. Income share by percentile (Altair, interactive)**
Pie chart with a year slider showing how the share of income held by each percentile group has shifted year by year. The slider replaced an earlier dropdown to make cross-time comparison faster and more intuitive.

**2. Linked income & inequality ratios (Altair, interactive)**
Two charts linked by hover tooltips — household income by percentile alongside the 90/10, 90/50, and 50/10 income ratios. Hovering reveals the difference in median income between the top and bottom percentiles for any year.

**3. Median personal income vs. median home prices (Altair, interactive)**
Shaded comparison of household buying power against housing costs over time, with a hover tooltip surfacing both metrics and their gap at any given year.

**4. Gini coefficient with historical annotations (matplotlib, static)**
A simple line chart of the Gini index from 1963–2022, annotated at the inflection points (Nixon Shock, Reagan-era tax cuts, the 1990 recession, 2008 housing bubble, COVID-19, etc.) to anchor the data in real-world events. Featured at the top of this README — see [`images/gini_index_annotated.png`](images/gini_index_annotated.png).

---

## Data Sources

- **World Bank Group** — income shares by percentile (1960–present) and Gini coefficient (1963–2022)
- **IPUMS USA** — housing permits, home prices, and median household income time series
- **Macro monthly dataset** (Kaggle, accessed via `kagglehub`) — supplemental macroeconomic context

The cleaned, pre-processed CSVs used in the notebook are hosted in a separate repo: [Taylorbeuke/Project3](https://github.com/Taylorbeuke/Project3).

---

## Repo Structure

```
us-economic-inequality-dataviz/
├── Project3Code.ipynb            # Main analysis + Altair/matplotlib chart construction
├── Income Inequality 2.pbix      # Power BI report — income inequality dashboard
├── gini_index.pbix               # Power BI report — Gini index focus view
├── images/                       # Screenshots of the StoryMap and final charts
│   └── gini_index_annotated.png  # Hero image — annotated Gini Index over time
├── README.md
├── LICENSE
└── .gitignore
```

> The `.pbix` files are Power BI Desktop project files. Anyone with [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free) can open them to explore the dashboards locally.

---

## Running the Notebook

The notebook was originally written in Google Colab. To run locally:

```bash
git clone https://github.com/<your-username>/us-economic-inequality-dataviz.git
cd us-economic-inequality-dataviz
pip install pandas altair matplotlib requests kagglehub
jupyter notebook Project3Code.ipynb
```

Two notes for local execution:

- The `from google.colab import files` line and any `files.download(...)` calls can be skipped or commented out — they're Colab-only conveniences.
- The notebook pulls the cleaned CSVs directly from the [Taylorbeuke/Project3](https://github.com/Taylorbeuke/Project3) repo over HTTPS, so no manual download is needed.

---

## Design Process & Iteration

This project went through two full design cycles. The first, with the group, established the data backbone and an initial set of visualizations. The redesign focused on three lessons learned:

- **Interaction design matters more than chart variety.** Replacing a dropdown with a slider, or expanding a hover region, changed how readers engaged with the same underlying chart far more than swapping chart types did.
- **Cohesive design is what separates drafts from published work.** Consistent fonts, color palettes, and tooltip behaviors across charts made the difference between "a notebook output" and "a published story."
- **Let the data shape the narrative, not the other way around.** Several charts were rebuilt mid-process when the data revealed a different story than the one originally sketched.

Read the full design retrospective in the [Medium article](https://medium.com/@taylorbeuke/70-years-of-u-s-economic-inequality-a5f2c7d88cc3).

---

## Acknowledgments

Original group project (*The Myth of the American Dream*) co-authored with Bruno Giron Giessen, Vincenzo Lidley, and Adri McCarville for INFO 4602 / MSBC at CU Boulder, Spring 2025.

## Author

**Taylor Beuke** — [Medium](https://medium.com/@taylorbeuke) · [GitHub](https://github.com/Taylorbeuke)
