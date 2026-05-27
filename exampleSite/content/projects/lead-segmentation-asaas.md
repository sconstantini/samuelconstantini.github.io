---
title: "High level Lead segmentation using NLP – ASAAS"
date: 2021-10-01
draft: false
tags: []
showInHome: false
---

## Overview

Before AI was a tool anyone could reach for, I built my own using NLP libraries, Python scraping, and a heatmap of cosine similarity scores to solve a problem that had no clean answer in any public database: who are our best potential customers, and what do they actually do?

## Context

- **Company:** ASAAS - Payments Fintech
- **Role:** Business Development Strategist
- **Period:** 2021
- **Markets:** Brazil

## Challenge

Our best clients were driving most of our revenue, but finding more companies like them was harder than it sounds. Brazilian public business registries (CNAE) were not so usefull, since a "Tickets Marketplace" and a SaaS company could both be listed under "Online Services". There was no reliable way to search by what a company actually does.
I needed to identify the real market segments of our top clients and use that signal to find lookalike leads at scale.

## What I Did

- Mapped top client cohorts, identifying the most profitable existing clients and extracted their website URLs as the starting point for analysis.
- Built a text scraping pipeline using requests and BeautifulSoup to collect and clean all visible text from each homepage, stripping scripts, styles, and HTML noise.
- Applied NLP keyword extraction, tokenized text, removed Portuguese stopwords, applied stemming (RSLPStemmer), and used keyword extraction to isolate the 20 most representative terms per site. This revealed that our best clients clustered around three segments invisible in any public database: Online Universities, Online Auction Platforms, and Tickets Marketplaces.
- Scraped lookalike leads from Google - for each discovered segment, collected the first 20 pages of search results and ran the same keyword extraction pipeline on every new URL found.
- Built a cosine similarity heatmap: vectorized all sites with TF-IDF and computed pairwise cosine similarity across the full set for each segment. The resulting matrix made it immediately clear which leads shared vocabulary with our best clients.
- Clustered and ranked using K-Means to group all sites by segment, then filtered for clusters that matched our ICP, producing a prioritized, intelligence-backed lead list.

## Results

- Discovered over 300 high-value leads, websites, numbers and emails for mass outreach
- Replaced hours of manual research with a repeatable, data-driven pipeline built entirely from open-source libraries
- Built before ChatGPT existed

## Gallery

![Description of image 1](/images/projects/icp1.jpg)

![Description of image 2](/images/projects/icp2.jpg)
