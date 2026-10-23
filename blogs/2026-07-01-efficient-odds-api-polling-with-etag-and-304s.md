---
title: "Efficient odds API polling with ETag and 304s"
url: "https://oddsrelay.io/blog/polling-an-odds-feed-efficiently"
date: "2026-07-01"
feed_url: "https://oddsrelay.io/blog/rss.xml"
---
Send the ETag back as If-None-Match and an unchanged reply is an empty 304 that costs no tokens.
