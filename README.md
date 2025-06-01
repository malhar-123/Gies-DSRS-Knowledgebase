# Gies-DSRS-Knowledgebase
DSRS Knowledge Base Project - README
- Overview
The Data Science Research Services (DSRS) at the University of Illinois provides researchers with data science consulting, secure infrastructure, licensed datasets, and advanced computing tools. This project creates an automated, structured knowledge base from DSRS's publicly available resources to aid new joiners, collaborators, and external researchers.

##-Project Purpose

This notebook crawls, indexes, and organizes DSRS-related content from:

https://dsrs.illinois.edu/

In future phases, it will expand to include:

https://github.com/giesdsrs

https://dsrs.illinois.edu/datahub/category

https://giesbusiness.illinois.edu/disruption-lab

The core output is a searchable, structured JSON and SQLite knowledge base.

##-Functionality Summary

Web Crawler: Extracts text from paragraphs, classifies it into logical sections.

Keyword Extractor: Identifies and indexes top keywords from each page.

JSON Export: Saves the knowledge base in a structured .json format.

Keyword Search: Allows users to retrieve relevant pages based on keyword matches.

Graph Visualization: Depicts conceptual data flows across DSRS components (Datasets → Projects → Services → Tools, etc.).

- Data Schema
Each crawled entry is structured using the following fields:

url: Source URL of the crawled page
title: Page or section title
section: Classified section (e.g., Services, Tools)
content: Main body text extracted from the page
keywords: Auto-extracted keywords (top 5) for quick retrieval
last_crawled: Timestamp of the last time the page was crawled

- How Users Can Interact
Search: Enter any keyword to retrieve matching knowledge entries.

Explore Graph: View how different DSRS resources conceptually relate.

Extend or Update: Add more URLs or re-run the notebook to refresh content.

- Maintenance Strategy
Each crawl stores last_crawled timestamps.

Duplicate pages are updated using ON CONFLICT logic.

Can be scheduled (via cron or GitHub Actions) to refresh monthly.

##-Future Scope

Iterative (BFS) Crawl: Switch to a breadth-first strategy to better prioritize public-facing summary pages.

Full Site Expansion: Crawl GitHub repositories, DataHub catalogs, and the Gies Disruption Lab.

Semantic Search: Add OpenAI or embedding-based models for natural language queries.

Onboarding Assistant: Build an FAQ/chat interface for new DSRS members or interns.

Knowledge Architecture: How DSRS Components Relate
Services → use Technical Tools like Azure, JupyterHub, and MinIO. Projects → are supported by Services (consulting, analytics) and Tools (secure compute, databases). Datasets → power Projects and are curated through DataHub. Internships and Collaborations → emerge from real-world application of Projects and Services.

This structure ensures a connected ecosystem: tools and services support research, which in turn enables learning, collaboration, and innovation.
