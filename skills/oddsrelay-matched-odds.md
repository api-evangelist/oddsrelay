---
name: oddsrelay-matched-odds
description: Find matched bookmaker back / exchange lay odds on OddsRelay, quoting the token price first.
api: OddsRelay API
operations: [listSports, listBookmakers, getMatchedBoard, getUsage]
---
1. Discovery is free: call listSports and listBookmakers (GET /v2/sports, /v2/bookmakers) to pick filters.
2. Call getMatchedBoard (GET /v2/odds/{type}) with region and filters plus quote=true to see the token cost for free.
3. Make the real call; send If-None-Match on repeats (304s are free) and Accept-Encoding: gzip.
4. On 402 insufficient_tokens narrow filters; on 429 wait Retry-After. Check getUsage for balance.
