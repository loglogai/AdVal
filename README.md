# AdVal

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-yvligo-ffd21e)](https://huggingface.co/loglogai/yvligo)
[![loglog.ai](https://img.shields.io/badge/web-loglog.ai-1f6feb)](https://loglog.ai)

AdVal (Advertisement Eval) measures how well an LLM agent runs a paid ad campaign on its own. The agent gets a client's
brief and a budget, runs the campaign on a simulated X (Twitter) Ads market, and is scored on what the client counts: the
free-trial starts, installs, sign-ups or purchases the campaign brings in.

This repository holds the agent traces: 630 complete runs, 14 LLM agents on the same 45 briefs.

## What it measures

Each task is a brief from a small business, written the way a client would write it. It gives:

- what the client sells and the one outcome they count;
- the flight's dates and time zone, and a total budget (100 to 2,700 USD);
- who can become a customer: the markets the product is sold in, the devices it runs on, sometimes a minimum age;
- a few posts the client has approved, which the agent can promote but not rewrite.

The agent runs the campaign alone, from launch to the end of the flight, through an emulated X Ads API: 78 MCP tools,
plus a scheduler that pauses until later in the flight.

1. **Set up.** Turn the brief into campaigns and ad groups: objective, targeting (locations, platforms, age, interests,
   keywords), bids, budgets, and which posts to promote.
2. **Manage.** Come back through the flight, read the stats, and move money to what works: pause, retarget, rebid,
   rebudget.
3. **Report.** End with a recap to the client.

The score is the conversions the campaign drove, against a scripted baseline (see [Scoring](#scoring)). Clicks and
impressions don't count, and the agent usually can't see what does: in 35 of the 45 briefs the client has no X pixel,
so X reports no conversions and the agent has to judge from clicks, reach and cost, and from what the brief says about
who buys. A good run finds the people who convert, doesn't pay to reach people who can't (the wrong country or
device), bids enough to deliver without overpaying, and spends the budget by the end of the flight: money left over
buys nothing. Besides the score, each run is checked on its recap, its targeting and its setup (see [Checks](#checks)).

The market is simulated, so no money is spent and outcomes are comparable across agents. Every agent ran each brief
once, at the same rollout seed, so all agents faced the same markets.

## Scoring

A run's score is its **expected conversions over par**. Par is a scripted baseline in the same world and seed: one ad
group on the brief's rules at X's default AUTO bid. 1.0 matches par.

| Agent folder | Harness | Model | Effort | Geometric mean ÷ par | Under par | Lowest | Recaps accurate | Runs passing targeting and setup checks | Average cost per run |
|---|---|---|---|---|---|---|---|---|---|
| `deepseek-v4.1-flash-sft-b3-dsh+tinker-low` | DeepSeek Harness | DeepSeek-V4.1-Flash, post-trained (see below) | low | 1.311 | 3 | 0.84 | 100% | 98% | $0.40 |
| `gemini-4-argon_Antigravity` | Antigravity CLI | `gemini-4-argon-medium` | medium | 1.198 | 8 | 0.68 | 100% | 80% | $2.14 |
| `gpt-6.1-sol` | Codex | `gpt-6.1-sol` | medium | 1.145 | 13 | 0.68 | 100% | 91% | $0.39 |
| `deepseek-v4.1-flash-dsh+api-low` | DeepSeek Harness | `deepseek-flash` (DeepSeek's API) | low | 1.095 | 15 | 0.53 | 98% | 89% | $0.02 |
| `grok-4.7_Grok_Build` | Grok Build | `grok-4.7` | medium | 1.087 | 12 | 0.43 | 100% | 73% | $2.05 |
| `opus-5.5` | Claude Code | `claude-opus-5-5` | medium | 1.068 | 12 | 0.76 | 98% | 89% | $2.50 |
| `gpt-6-astra` | Codex | `gpt-6-astra` | medium | 1.058 | 22 | 0.66 | 100% | 98% | $2.11 |
| `muse-spark-1.3_Muse_Code` | Muse Code | `muse-spark-1.3` | medium | 1.041 | 10 | 0.60 | 98% | 98% | $0.30 |
| `inkling-2-small` | Claude Code (Tinker's API) | `thinkingmachines/Inkling-2-Small:peft:262144` | medium | 1.023 | 19 | 0.55 | 89% | 93% | $0.08 |
| `haiku-5.5` | Claude Code | `claude-haiku-5-5` | medium | 1.012 | 19 | 0.37 | 100% | 96% | $0.08 |
| `muse-wonder-1.0_Muse_Code` | Muse Code | `muse-wonder-1.0` | medium | 1.007 | 13 | 0.42 | 100% | 98% | $0.65 |
| `sonnet-5.5` | Claude Code | `claude-sonnet-5-5` | medium | 0.930 | 23 | 0.44 | 100% | 89% | $0.75 |
| `gpt-6-luna` | Codex | `gpt-6-luna` | medium | 0.738 | 14 | 0.00 | 89% | 93% | $0.02 |
| `nvidia--nemotron-3.5-lightning` | Claude Code (OpenRouter) | `nvidia/nemotron-3.5-lightning` | medium | 0.213 | 38 | 0.00 | 38% | 40% | $0.09 |

A run that bought nothing scores 0 and counts as 0.001 in the geometric mean. One agent's score on the same brief
varies by about 10% from run to run, and each brief here was run once. Recaps accurate and runs passing targeting and
setup checks are shares of the 45 runs, from the [checks](#checks), which don't change the score.

Average cost per run is averaged across all 45 briefs at API prices. yvligo costs more than its base model
(`deepseek-v4.1-flash-dsh+api-low`) because it is served on Tinker.

The first row is [yvligo](https://huggingface.co/loglogai/yvligo): DeepSeek-V4.1-Flash-1017 post-trained with supervised
fine-tuning on expert traces, a LoRA adapter served on Tinker. It ran in DeepSeek Harness at low effort, the same setup
as the `deepseek-v4.1-flash-dsh+api-low` row, which is the same model before post-training. Its `result.json` names
the model as DeepSeek Harness does (`deepseek-flash`).

## Checks

Besides the score, the eval checks each run three ways. Each run's `result.json` has the results: `recap_check`,
`recap_metrics`, `targeting` and `failed_checks`.

- **Recap.** A model (Claude Haiku 5.5) reads the agent's last message and reports, as JSON, the whole-campaign totals
  it states for spend, impressions and link clicks, with the text each comes from. Code then compares them with what
  the campaign delivered, as the reports showed it when the agent ended or at the end of delivery. `accurate`: every
  stated total within 2%; `wrong`: one further off; `no recap`: neither spend nor link clicks stated. `recap_metrics`
  has, per stated metric: how the message states it (`kind`: one `total`, a `range`, or only `parts` of the whole,
  which count as their sum), the text (`quote`), the total (`stated`; a range is `[low, high]`), the true totals when
  the agent ended (`visible`) and at the end of delivery (`final`), its relative error from the nearer one (`error`)
  and whether that is within 2% (`right`).
- **Targeting.** The spending ad groups together, on each of location, platform, age and gender, against what X's
  policy allows for the product's category and against who the brief says can convert. Each is `laxer` (reaches past
  it), `exact` or `stricter` (leaves people out). A run fails when it:
  - reaches past the brief's markets or platforms, paying for people who can't convert;
  - is stricter than both X's policy and the brief: a market or platform left out, gender targeting, or an age gate
    neither asks for.

  Splitting markets or platforms across ad groups passes. Reaching below the brief's minimum age doesn't fail: X
  only age-targets people whose age it knows, so an age gate also drops adults of unknown age.
- **Setup.** A run fails when:
  - X disapproves one of its ad groups under its policy for a restricted category (11 briefs: financial services,
    political campaigning and alcohol);
  - the budgets it left could spend more than 5% past the client's;
  - it left an ad group running past the flight's end;
  - it ran a post the client didn't approve.

## Layout

```
index.csv                       one row per run: agent, harness, brief, grade, par, grade ÷ par, spend, minutes,
                                recap check, failed checks
runs/<agent>/<brief>/
    brief.md                    the brief and approved posts, as the agent saw them
    trace.json                  every tool call: simulated time (at), tool, arguments, result
    events.jsonl                the harness's own event stream: the model's reasoning, messages and tool calls
    recap.md                    the agent's final message to the client
    result.json                 outcome: grade (expected conversions), par, grade ÷ par, conversions, link clicks,
                                impressions, spend, budget left, tool counts, minutes, harness, model, effort;
                                checks: recap check and its claims against the true totals, targeting fit per
                                dimension, failed checks
```

`events.jsonl` is each harness's native format, so it differs between Claude Code, Codex, Grok Build, Antigravity
CLI, DeepSeek Harness and Muse Code. `trace.json` has the same format for every agent.

## Notes

- **Simulated.** No real ads ran and no money was spent. The X Ads API, its delivery and the people who convert are
  simulated. The dates the agents see are the campaign's simulated dates.
- **Isolated.** Each agent ran in a sandbox with only the campaign tools: no shell, files or web. Sandbox paths in the
  traces are replaced with `<sandbox>`.
- **Not included.** The briefs' hidden world parameters, which define who converts and how, are not part of this
  repository.

## License

MIT. See [LICENSE](LICENSE).
