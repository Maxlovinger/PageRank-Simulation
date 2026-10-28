# PageRank-Simulation

An interactive PageRank visualizer. Draw a small web of pages, and watch the PageRank scores converge step by step while a "random surfer" moves around the graph.

## How to use it

- Click an empty spot to add a page (up to 8)
- Click one page, then another, to add a link
- Right-click a page to delete it, Esc to cancel a selection
- **Random Web** makes a random graph
- **Run** / **Step** run the power iteration automatically or one step at a time
- Sliders set the damping factor α and the animation speed

## What it shows

- **Web graph** - the pages and links, with the surfer either following a link (probability α) or teleporting to a random page (probability 1 − α)
- **Google matrix** - built live from the graph:
  - S is the column-stochastic link matrix: column j spreads page j's rank evenly over its out-links, and a page with no out-links spreads evenly over every page
  - G = α·S + (1 − α)·(1/n)·J, where J is the all-ones matrix
- **Power iteration** - each step computes v(k+1) = G · v(k), with a history of every iteration
- **PageRank scores** - the current rank of each page

## Run it

It's a single HTML file with no dependencies. Open `pagerank.html` in a browser.

`vercel.json` serves `pagerank.html` at the root when it's deployed on Vercel.
