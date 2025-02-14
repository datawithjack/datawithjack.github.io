---
layout: project
title: CMJ Adaptive Range Monitoring Dashboard
image: /assets/img/portfolio/vald-adaptive-range.jpg
# accent_image: 
#  background: url('/assets/img/blog/jj-ying.jpg') center/cover
#  overlay: false
accent_color: '#ccc'
theme_color: '#ccc'
description: >
  Monitoring athlete readiness to trains using CMJ and adaptive ranges.
invert_sidebar: false
sitemap: false
date: 2025-01-15
categories: [portfolio, powerbi]
---
## CMJ Adaptive Range Monitoring Dashboard
I developed this dashboard to enhance athlete monitoring. It integrates CMJ (Countermovement Jump) metrics from the VALD ForceDecks system with adaptive ranges using Expectation-Maximization (EM) approximation in Power BI and R.

For more on adaptive ranges using EM approximation click [here](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0247338)

## Project Overview
- **Data Integration:** Imported athlete force plate data from VALD ForceDecks into Power BI.
- **Statistical Modeling:** Used R to apply EM approximation, allowing adaptive reference ranges to evolve dynamically based on individual athlete trends.
- **Visualization & Insights:** Built a Power BI dashboard to provide longitudinal monitoring of athlete performance, highlighting deviations and trends over time.

## Key Features
- **Adaptive Ranges:** Automatically adjust based on the athlete’s historical data.
- **Seamless Power BI & R Integration:** Enables advanced statistical analysis within an interactive Power BI report.
- **Scalability:** Designed to be easily deployed across teams in an organization.

## Interactive Report

<iframe title="CMJ Monitoring Report (With Pre Calc Adaptive Range)" width="800" height="636" src="https://app.powerbi.com/view?r=eyJrIjoiNzJhMWY4ZTctMmY2Zi00MTRjLWI2OTktZjAyNDBiOTUzYzVjIiwidCI6IjRlNDc4YWIwLWFjYWUtNGRiNS1hYjA4LTQ0ZjdlOTliNDc1MiJ9" frameborder="0" allowFullScreen="true"></iframe>

## Next Steps
- **Connect directly to the VALD API** for real-time, in-session monitoring.
- **Enable parameter customization** for adaptive range calculations.


This project builds on the great work of [Kenny McMillan PhD](https://lnkd.in/dyUSkZsU) and aims to provide a robust, data-driven approach to athlete performance tracking. 



