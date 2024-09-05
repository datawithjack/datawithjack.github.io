---
layout: project
title: 'Road to Paris 2024 - Fencing Qualification'
caption: Tracking fencing athletes progress towards qualification for the 2024 Paris Olympic Games
description: >
  Dashboard showing the Olympic Qualification for Women's Epee Teams from the Americas.
date: '01-09-2023'
image: /assets/img/projects/fencingtest.jpg
sitemap: false
---

## Fencing Qualification Dashboard for the 2024 Olympic Games

### Table of Contents
1. [Project Overview](#project-overview)
2. [Fencing Qualification Process for the 2024 Olympics](#fencing-qualification-process-for-the-2024-olympics)
3. [Challenges](#challenges)
4. [Skills Developed](#skills-developed)

### Project Overview

The goal of this project was to build a Power BI dashboard that tracks and displays the qualification process for the 2024 Olympic Games in fencing. With the Olympics now underway, I’ve updated the report to reflect the qualification progress throughout the entire qualification period. The dashboard provides users with a comprehensive view of the qualification standings, including the following key insights:

- **Current Rankings After Each Event**: The dashboard tracks and updates rankings after every qualifying event.
- **Athletes in Qualification Positions**: It highlights athletes who have secured a place for the 2024 Olympics.
- **Athletes in Contention**: It also tracks athletes who are on the cusp of qualification and still have a chance to qualify.

### Fencing Qualification Process for the 2024 Olympics

The qualification for the Paris 2024 Olympics in fencing is divided across six categories: Men’s and Women’s Épée, Sabre, and Foil. Qualification is determined through both **team** and **individual** pathways, with specific rules to ensure global representation.

- **Team Qualification**: The top 4 teams in each fencing category automatically qualify for the Olympics based on points accumulated in major competitions, including the Senior Team World Cup, Senior Team World Championships, and Senior Team Continental Championships. Additionally, the highest-ranked team from each continent (Europe, Asia-Oceania, Africa, and the Americas), ranked between 5th and 16th, will also qualify. If no team from a particular continent is within this range, the next highest-ranked team, regardless of continent, qualifies instead.

- **Individual Qualification**: For fencers whose teams have not qualified, the top 6 athletes from each category will qualify, distributed as follows:
  - 2 from Europe
  - 2 from Asia-Oceania
  - 1 from the Americas
  - 1 from Africa
  
  Individual qualification is based on points earned from events like the Individual Grand Prix, Individual World Cup, and Continental and World Championships.

- **Zonal Qualification**: After the primary qualification period ends, there is a final opportunity for fencers to qualify through Zonal Qualifying Tournaments. One fencer per nation (without a qualified team or individual) can compete, and the winner of each tournament in each category will earn a spot at the Olympics.

This process ensures that the best fencers from around the world, across various continents, have the opportunity to compete in Paris 2024.

For more detailed and official qualification criteria, please refer to the official document provided by FIE: [Official Qualification Criteria for Paris 2024 – Fencing](https://static.fie.org/uploads/28/140899-Olympic%20Games%20Paris%202024%20qualification%20system%20-%20Fencing%20-%20English.pdf).

### Challenges

The biggest challenge in this project was data quality. The data needed extensive cleaning to resolve inconsistencies, missing entries, and formatting errors that could affect the accuracy of the dashboard.

Another significant challenge was implementing the complex logic for the qualification process. Each fencing category had its own set of rules for both team and individual qualification, and the logic had to account for multiple layers such as continental quotas, individual rankings, and zonal tournaments. This required careful use of advanced DAX formulas and a clear understanding of the qualification rules to ensure the dashboard accurately reflected the current standings.

### Skills Developed

During this project, I developed the following skills:

- **Advanced DAX**: Used to apply complex logic and conditionally format values in matrix visuals based on qualification rules.
- **Data Cleaning in M Query**: Ensured that the data was properly structured, consistent, and ready for analysis by resolving formatting issues and filling in missing data.
