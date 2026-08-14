IPL Ball-by-Ball Analysis (2008-2024)
I wanted to go beyond a basic "who won the most matches" project, so I picked up the full IPL ball-by-ball dataset (1,095 matches, 260K+ deliveries from 2008-2024) and tried to answer some questions I was genuinely curious about as a cricket fan — not just questions that sound good on a resume.

Dataset
IPL Complete Dataset 2008-2024 from Kaggle — two files, matches.csv and deliveries.csv. If you want to run this yourself, download both and drop them in the same folder as the notebook.

Tools
Python, pandas, matplotlib, Jupyter Notebook.

What I wanted to find out
Does batting first actually help, or is chasing better?
Who are the real death-overs specialists (not just by reputation)?
Which top batsmen are consistently good vs. streaky?
Does winning the toss actually matter as much as people say?
Which grounds are batting paradises and which favor bowlers?
What I found
Chasing wins more often. 54.1% of matches were won by the team batting second, vs 45.9% for teams batting first. Makes sense honestly — chasing teams know exactly what target they need and can pace the innings around it, whereas the team batting first is often guessing at a "par" score.

Death overs economy — Sohail Tanvir tops the list, but it comes with an asterisk. He's got the best economy rate (6.84) in overs 16-20, but he's only bowled about 18 overs in that phase total. SP Narine, on the other hand, has bowled 174 overs at 7.4 economy — way more overs, still a great number. If I had to trust one for a T20 death-overs role, I'd lean Narine just because there's way more data behind that number.

Consistency vs boom-or-bust. I calculated each top batsman's average runs per innings and divided that by their standard deviation (basically: how much do their scores swing game to game). Faf du Plessis and Matthew Hayden came out as the most reliable — solid outputs most games, no huge dips. Chris Gayle was the opposite — high average, but also the most unpredictable of the group, which honestly tracks with how most people would describe him as a player. Some games he destroys the bowling, other games he goes cheap.

Toss doesn't matter as much as commentators make it sound. I expected a pretty steady advantage for whoever wins the toss (there's a lot of talk about dew affecting evening chases), but the data doesn't really back that up — it swung from 42% to 61% year to year with no clear pattern. My guess is toss matters a bit at specific venues/seasons but isn't some universal law of IPL cricket.

Chinnaswamy is a batting paradise, as everyone already knows. Bengaluru's ground averaged ~380 runs per match, matching its reputation as one of the flattest, most batter-friendly pitches in the league. One thing I noticed though — a couple of venues showed up as both "highest scoring" and "lowest scoring" depending on how I sorted it, which turned out to be because they'd only hosted 1-2 matches total, so the average wasn't really meaningful. Had to filter those out to avoid drawing conclusions from basically no data.

A note on methodology
For the consistency question, I used something called coefficient of variation (std dev ÷ mean) instead of just looking at averages — a straight average would've missed the whole "consistent vs explosive" distinction, which was really the point of that question.

I also filtered out bowlers/venues with very small sample sizes before ranking anything, since a bowler who's bowled 12 balls in death overs with a great economy rate doesn't really tell you anything reliable.

Files
ipl_analytics.ipynb — the notebook, code + charts + notes all in one place
A couple of caveats
2009 season was played in South Africa and 2020/21 in the UAE (COVID), so venue/scoring comparisons across all seasons aren't perfectly apples-to-apples.
Some venues only hosted a handful of matches, so their averages should be taken with a pinch of salt.
