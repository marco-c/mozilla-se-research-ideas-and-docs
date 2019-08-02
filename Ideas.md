## Empirical studies

### test-verify to reduce flaky tests
Study the effects of test-verify \[1\]. Are test-verified tests less likely to become intermittent than others? How long does it take for a test to become flaky? Could running test-verify periodically reduce the risk of tests turning flaky?

\[1\]: <https://developer.mozilla.org/en-US/docs/Mozilla/QA/Test_Verification>

### Do developers evaluate risk correctly?
When requesting uplift \[2\], developers state the risk associated with the patch for which they are requesting uplift. Do they evaluate risk correctly? Are they aware of the risks? What are the characteristics of the patches for which developers are not able to evaluate risk correctly? Does "release rush" affect the evaluation?

\[2\]: Marco Castelluccio, Le An, and Foutse Khomh - An empirical study of patch uplift in rapid release development pipelines. Empirical Software Engineering (EMSE), Nov 2018.

### What is the impact of larger and more diverse Nightly populations?
What are the effects of a larger Nightly population? Are there more bugs filed? Are there more bugs fixed? Is there crash data which is more representative of the release population?

### Study changes in processes and software metrics after the removal of Aurora
Mozilla recently dropped the Aurora channel \[3\]. What changed? Are features shipped to users more quickly? Are there more regressions?

\[3\]: <https://release.mozilla.org/firefox/release/2017/04/17/Dawn-Project-FAQ.html>

### Study Outreachy/GSoC reviews
Study the interactions between mentors and mentees in open source projects on review systems, chat, and so on. Derive a set of suggestions for mentors and mentees to be effective.

### mozregression - Bisection for the masses
Study the effects of mozregression usage by Mozilla contributors. Does mozregression reduce the amount of time to fix a bug?

### Evaluate SZZ with manually annotated Bugzilla information
We have recently introduced a "Regressed By" field on Bugzilla, to specify what caused a given bug. SZZ results could be evaluated by using this data, and a study of what kinds of bug-introducing commits are missed could be done (maybe finding ways to improve SZZ to catch these other kinds of bug-introducing commits).


## Tools

### Use crash stack traces to automatically assign crashes to teams
From the stack traces, it should be possible, using ML techniques, to automatically assign a crash group to a given team (filing a bug in the right component).

### Cluster crashes using NLP techniques
Evaluate clustering crashes using NLP techniques (stack trace being a sentence, and function names being words), e.g. doc2vec for word embedding and WMD as a distance metric. WIP project at \[4\].

\[4\]: <https://github.com/marco-c/crashsimilarity>

### Detect abnormal changes between components
Detect abnormal changes (e.g. using causal impact or something similar) between components (in # bugs, # lines of code, and other metrics). This can be useful to detect if something is suddenly going wrong e.g. after the release of a new feature.

### Reinforcement learning for static analysis warnings
Static analysis tools can have false positives. Using reinforcement learning, we could train an agent to figure out when a warning should be shown and when it should not be shown (using information from past warnings and how developers acted on them as positive/negative reward).
