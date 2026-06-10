# How Many People Can Bench 225 / 315 / 405?

I wanted an actual answer to this, not just a gym-bro guess. So I built a statistical model using 3+ million real competition lifts to estimate how many people on earth can hit each milestone, with real confidence intervals.

## Why most estimates are wrong

The typical approach is to take some global gym membership number and apply it evenly across 8 billion people. That doesn't work. ~22% of Americans resistance train. In sub-Saharan Africa it's under 2%. And even among people who lift, barbell bench is way more common among men than women.

This model accounts for that by splitting the world into 10 regions, each with its own lift rate, strength baseline, and uncertainty range. Everything is calibrated to real survey data (IHRSA, CDC BRFSS, Eurobarometer) and scaled to regional average bodyweight.

## How to run it

```bash
pip install -r requirements.txt
jupyter notebook bench_world_model.ipynb
```

The OpenPowerlifting dataset (~200MB) downloads automatically on first run and caches locally after that.

## What's in the notebook

| Chapter | What it covers |
|---|---|
| 1 | Download and clean 3M+ OPL competition records |
| 2 | Why strength follows a log-normal distribution, not a bell curve |
| 3 | The gap between competitors and casual gym-goers |
| 4 | Regional breakdown - gym culture is not evenly distributed |
| 5 | Monte Carlo simulation - why a range is more honest than one number |
| 6 | Reveal: 225 lbs |
| 7 | Reveal: 315 lbs |
| 8 | Reveal: 405 lbs |
| 9 | Full drop-off curve from 100 to 500 lbs |
| 10 | Sensitivity analysis - what actually drives the uncertainty |
| 11 | All three side by side |

## Key takeaway

North America and Europe are about 8% of the world's population but account for the majority of people who can bench 315+. The bottleneck isn't biology - it's gym access, training culture, and average bodyweight. The single biggest unknown in the whole model is just: how many people globally actually pick up a barbell?

## Data sources

- OpenPowerlifting - openpowerlifting.org (CC BY 4.0)
- UN World Population Prospects 2024
- IHRSA Global Report 2023
- CDC BRFSS (US lift rate)
- Eurobarometer / EHIS (European lift rate)
- NSCA normative tables (strength baseline calibration)
