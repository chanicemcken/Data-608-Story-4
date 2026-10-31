# Data Practitioner Salaries: How Occupation and Geography Shape Pay

**Python · pandas · BLS API · Data validation · Exploratory data visualization**

## Overview
An exploratory data story examines how **annual mean wages** differ among selected U.S. data-related occupations and states. It combines government wage data, documented occupational proxies, coverage checks and visual comparisons.

**Question:** How much does average pay vary by occupation and geography for selected data-practitioner roles?

## Data source and scope
Data come from the [U.S. Bureau of Labor Statistics Occupational Employment and Wage Statistics (OEWS)](https://www.bls.gov/oes/), retrieved through the [BLS Public Data API](https://www.bls.gov/developers/).

The analysis uses five official occupation categories as **proxies** for commonly discussed data roles:
- Data Scientists
- Database Architects
- Computer Systems Analysts
- Operations Research Analysts
- Statisticians

These categories do not exactly correspond to every job title advertised as data analyst or data engineer. Reported wages are **annual means**, not medians, offers, or take-home pay.

## Analytical workflow
1. Construct BLS wage-series identifiers for selected state/occupation combinations.
2. Request observations in batches with retry handling and validate numeric wage values.
3. Select a common available reporting year with sufficient coverage rather than mixing wage years.
4. Explore occupation- and state-level differences with comparative charts.
5. Document missing or suppressed occupation–state combinations and limits of interpretation.

## Files
- [Google Colab / Jupyter notebook](DATA_608_Story_4.ipynb)
- [Python source](data_608_story_4.py)
- [Report PDF](DATA_608_Story_4.pdf)

## Reproduce
1. Open `DATA_608_Story_4.ipynb` in Google Colab or Jupyter.
2. Run the notebook using Python with `requests`, `pandas`, `numpy`, `matplotlib`, and `seaborn` installed.
3. The notebook requests BLS observations live; it needs internet access and may encounter BLS rate limits, outages, or suppressed series.
4. The script can export a dated CSV snapshot of the selected wage observations. For repeatable comparisons, save and reuse that snapshot rather than assuming a future live query will return the same year or coverage.

## Limitations
Geographic pay differences do not account for cost of living, role seniority, education, employer, remote-work policy or job availability. OEWS estimates may be suppressed for some state/occupation combinations, and proxy categories should not be interpreted as exact title matches. This is descriptive analysis, not a causal estimate of the effect of moving states.

*Academic data-story project — DATA 608.*
