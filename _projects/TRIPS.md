---
layout: project
title: The Rest is Politics- - People, Places & Organisations
image: /assets/img/portfolio/trips_screenshot1.jpg
# accent_image: 
#  background: url('/assets/img/blog/jj-ying.jpg') center/cover
#  overlay: false
accent_color: '#ccc'
theme_color: '#ccc'
description: >
  Exploring the people, places and organisations of The Rest is Politics podcast using the Spotify API.
invert_sidebar: false
sitemap: false
date: 2024-05-01
categories: [portfolio, powerbi]
---
## The Rest is Politics- - People, Places & Organisations
## About this project

### Introduction:

The idea for this report was inspired by Injae Park’s a.k.a ‘Power BI Park' incredible Advanced Power BI Project video that used Python, ChatGPT, HTML, and Deneb to create a stunning Power BI report.

[Advanced Power BI Project - Injae Park](https://www.youtube.com/watch?v=ZSrVOyKAC4Y&ab_channel=PowerBIPark)

My primary objectives for this project were to continue to develop skills in the following areas:

* Deneb Visuals
* Python (APIs & Text Analysis)
* HTML Visual
* Word Clouds (I had never used this before)
  
### Data Extraction and Analysis:

Using the Spotify API, I collected episode data from the "Rest Is Politics" podcast. The API doesn’t provide the richest datasets for podcasts (unless I've missed something :)) but my aim with this report was to play around with some of the visuals I had little to no experience using so I continued.

Despite the dataset's modest size and depth, I was still able to employ text analysis techniques to extract relevant entities such as names, places, and organizations using the spacy Package from episode title and description field. The dataset also provided an audio preview URL link which allowed me to incorporate a novel HTML visual in the tooltip within the report.

### Building the Interactive Report:

I spent a good amount of time exploring different designs via sketching before I started building my report. I always like my reports to be as simple as can be and where possible fun (especially if I’m doing them for pleasure!) and given that this report was about experimenting with new visuals I tried to keep use of my core visuals to a minimum.

I was slightly disappointed with the lack of customisation of the word cloud visual although I think it fits my report however I was very happy with the timeline I created using Deneb (links below to resources I used) and the tooltip HTML audio player! The audio player is probably a little over the top for a professional setting but for a personal project, I think it was a ‘fun’ addition. The timeline however I have since used at work.

### Conclusion:

Despite the modest nature of the dataset, this project allowed me to continue to develop my Python skills while simultaneously introducing me to a whole new realm of custom visualisations through the Power BI Deneb visual. Moving forward, I am excited to apply the knowledge and techniques gained from this project to future endeavors in data analysis and visualization.

I have tried to keep this write-up brief and informal if you have any questions please feel free to reach out in the comments or on LinkedIn.

### Future Steps:

I was initially hoping that the API would provide a complete audio transcript so that I could perform a more in-depth text and sentiment analysis. I have seen transcripts available on some websites but that is going to require some serious upskilling in my web scraping skills. 😊

### Resources:

[Power BI - Timeline with conditional markers (Deneb / Vegalite) — Day to Data Stuff](https://www.daytodatastuff.co.uk/deneb/powerbi-deneb-timeline-with-conditional-markers)

