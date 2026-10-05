# PC FC Scouting Platform

A proof of concept of the scouting and recruitment platform proposed in the term project
*Developing a Scouting Infrastructure for a Football Team* (Rushikesh Kulkarni, EMGT 5220
Engineering Project Management, Northeastern University, Spring 2024).

It is a single web page with no build step and no server. Open `index.html` in a browser.

## What it shows

| Section | What it does |
|---|---|
| Overview | Headline counts, highest-rated targets, rating against estimated fee, latest scout reports |
| Players | Central player database with search, filters, sortable columns and adjustable evaluation weights |
| Player profile | Percentile metrics against position peers, season history, fit checks, fee comparison, scout report form |
| Compare | Up to three players side by side with a radar chart |
| Pipeline | Six recruitment stages from shortlist to signed, tracked against a transfer budget |
| Network | Regional hubs, scouts, a message channel per region, and a form to add scouts |
| Model & plan | How the score is calculated and how the demo maps to the project's work breakdown structure |

## How a player is scored

- **Current performance**: each metric becomes a percentile among players in the same position, averaged with position-specific weights.
- **Potential**: performance plus an allowance for each year under 25 and the trend in the player's season history.
- **Scout rating**: the mean rating across scout reports. Players with no report are scored on the other inputs.
- **Fit**: the mean of medical availability, character profile and cultural adaptation.

The evaluation is the weighted mean of the four (default 40 / 30 / 15 / 15).

## Limits

- All players, clubs, scouts, messages and figures are invented. A fixed random seed generates the same 140-player database on every load. Any match with a real person is a coincidence.
- The evaluation is a transparent scoring formula. It stands in for the trained machine-learning models described in the project plan.
- The transfer budget (EUR 45m) and the six scouting regions are placeholders, not figures from the report.
- Changes (pipeline moves, reports, messages, weights) are saved in the browser's local storage only. There are no logins and nothing is shared between users.
- Not covered: real data sources, video analysis, data-privacy controls, multi-user access.

## Hosting

To publish with GitHub Pages: Settings → Pages → Deploy from a branch → `main`, folder `/ (root)`.
