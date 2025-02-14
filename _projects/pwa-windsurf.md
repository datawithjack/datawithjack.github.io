---
layout: project
title: Exploring PWA Windsurfing Stats with Power BI and Python
image: /assets/img/portfolio/pwa-screenshot.jpg
# accent_image: 
#  background: url('/assets/img/blog/jj-ying.jpg') center/cover
#  overlay: false
accent_color: '#ccc'
theme_color: '#ccc'
description: >
  Exploring windsurf results data from the 2024 PWA Gran Canaria Event.
invert_sidebar: false
sitemap: false
date: 2024-11-15
categories: [portfolio, powerbi]
---
# Exploring PWA Windsurfing Stats with Power BI and Python

This project combines windsurfing and data analytics, using Python to scrape competition results from the Gran Canaria Windsurf World Cup event page and visualize them in Power BI.

## Data Collection with Python

I used Python to scrape event results from the official PWA website. The data was embedded within dynamically generated HTML elements, requiring the use of Selenium to navigate event pages and BeautifulSoup to extract structured data. The script collected heat results, jump scores, and wave scores, organizing them into a structured dataset for analysis.

Dataset on Sports Insights Hub GitHub: [View the dataset](https://lnkd.in/dQpRqSh3)

## Power BI Dashboard

Once the data was collected, I built an interactive Power BI report that highlights:

- The best heats, jumps, and wave scores for both men and women.
- Rider-level breakdowns, event summaries, and detailed results analysis.

The report follows a design similar to the PWA website, maintaining visual consistency with the sport’s official style while ensuring usability and interactivity.

A key feature of the dashboard is a custom elimination visual created with Deneb and Vega-Lite. This visual tracks rider progression through each round, incorporating a scatter plot to enhance the results tooltip.

The dashboard is embedded on GitHub Pages for easy access.

## Future Plans

In 2025, I plan to expand this project to include SlalomX, Foil Slalom, and Freestyle events. The goal is to develop a template for live event updates.

If you're interested in sports data visualization or have feedback, feel free to reach out.

### Explore the Report



Interactive Power BI report: [View the report](https://lnkd.in/dnry_JCP)  





