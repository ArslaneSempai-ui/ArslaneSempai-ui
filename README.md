## Arslane Chaouche Ramdane

Six years inside financial-crime operations — **30,000+ customer profiles reviewed,
6,000+ high-risk escalations, zero regulatory breaches** — now building the systems I
spent those years working around.

I write tools that **know their limits and prove it in numbers**. Every one of them
refuses, escalates, or reports a cost rather than producing a confident answer it can't
defend.

### → [arslanesempai-ui.github.io](https://arslanesempai-ui.github.io/)

**Put your own volumes in and the arithmetic runs in your browser.** Nothing is uploaded.
Every amount tells you whether it came from your figures, from a point you observed, or
from an assumption — and the three are never mixed.

---

### The six

| | The finding | Where it comes from |
|---|---|---|
| **[alert-triage-economics](https://github.com/ArslaneSempai-ui/alert-triage-economics)** | Seven analysts of eight are paid to handle nothing, and the next true positive is **free** down to threshold 0.45 — after which it costs $85,846 | The cost is bought in steps, not units. Funding part of a step buys nothing — not less, nothing. |
| **[process-cycle-time](https://github.com/ArslaneSempai-ui/process-cycle-time)** | 6.4 days end to end, of which **2.3 hours** of actual work. 74 distinct routes through a process that documents one | The mean describes no case: clean files finish in 2.4 days, twice-returned ones take 21.6. A target set on the mean is met by every case that never had a problem. |
| **[funnel-economics](https://github.com/ArslaneSempai-ui/funnel-economics)** | The biggest leak is **not** the best place to spend: 31.1× against 2.1× per dollar | And the ranking is not stable. "The signup page has already been rebuilt twice" is the most ordinary of four scenarios, and it moves signup from first place to third. |
| **[kyc-triage-agent](https://github.com/ArslaneSempai-ui/kyc-triage-agent)** | 58 % of files decided without a human and **zero** uncontrolled onboardings, on 400 cases | The threshold was inert: 111 of the escalations come from a rule that is certain, and no slider will move those. |
| **[regression-bench](https://github.com/ArslaneSempai-ui/regression-bench)** | Across three deterministic versions, 13 → 19 of 22 cases — and the third **breaks two** while its score rises | A rising pass rate is not an improvement. The fourth version races a clock and gets no score at all: publishing one would be publishing a draw. |
| **[compliance-document-search](https://github.com/ArslaneSempai-ui/compliance-document-search)** | On 25 questions: 10 right, 9 wrong, and **6 times it said nothing** — every time no answer existed | The two populations overlap and the bar sits inside the overlap. No position separates them; each one trades silences against inventions. |

Node with native TypeScript, no build step, **no runtime dependencies**, everything runs
locally. **147 tests.** Synthetic data throughout and labelled as such; the regulation is
real and cited.

---

### What I keep finding

**Conclusions don't transfer between corpora.** The same retrieval engine, measured on two
document sets, gave inverted results — keywords level with embeddings on one, far behind
on the other. What transfers is the method, never the settings.

**You can't tune your way out of a missing input.** Twice now, a threshold that looked
like the problem turned out to be inert, and the gain came from giving the system context
it didn't have.

**A number without its condition is not a measurement.** Every screen states the bar it
was judged against, the sample it rests on, and stays silent when the sample is too small
to mean anything.

**The bugs worth writing down are the ones the tests couldn't see.** A cost model that
crashed on the first event log where every case had come back, because its own log always
contained a clean one. A screen that rendered blank because two functions shared a name.
Both now have a test; neither could have been reasoned about in advance.

---

### Before this

AML/KYC and banking operations — BNP Paribas, Société Générale, Viva Wallet, and a
fintech AML operation. At Société Générale I led five analysts and cut our false-positive
escalation rate by around 18 %.

That rate was never a metric on a slide. It was the size of the pile on my desk, and it
is why every tool here is built around what an automated decision costs the people who
have to live with it.

📍 Athens, relocating to New York · 🇫🇷 🇬🇧 · [LinkedIn](https://www.linkedin.com/in/arslane-chaouche-ramdane-95595a388/)
