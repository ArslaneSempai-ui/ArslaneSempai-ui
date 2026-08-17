## Arslane Chaouche Ramdane

Six years inside financial-crime operations — **30,000+ customer profiles reviewed,
6,000+ high-risk escalations, zero regulatory breaches** — now building the systems I
spent those years working around.

I write tools that **know their limits and prove it in numbers**. Every one of them
refuses, escalates, or reports a cost rather than producing a confident answer it can't
defend.

---

### The four

| | What it does | What it proves |
|---|---|---|
| **[compliance-document-search](https://github.com/ArslaneSempai-ui/compliance-document-search)** | Answers from a compliance manual by quoting the passage — or refuses | Retrieval alone **cannot** say "I don't know". Refusal is a design decision with a measured cost: 75 % of unanswerable questions correctly refused, at one good answer in sixteen. |
| **[kyc-triage-agent](https://github.com/ArslaneSempai-ui/kyc-triage-agent)** | Applies an onboarding procedure, cites the clause, escalates when unsure | The escalation threshold was **inert**. One under-informed rule drove 125 of 146 wasted escalations; giving it the missing context took automation from 39 % to 55 % with no loss of safety. |
| **[regression-bench](https://github.com/ArslaneSempai-ui/regression-bench)** | Compares two runs and says what changed, not what scored | Fuzzy name matching raised the pass rate from 82 % to 86 % **while making two distinct people indistinguishable**. A rising average is not an improvement. |
| **[alert-triage-economics](https://github.com/ArslaneSempai-ui/alert-triage-economics)** | Prices a detection threshold in analyst hours, headcount and money | Eight analysts in post, seven idle, 392 of 454 detections missed — and **306 of them catchable for nothing**, because the payroll was already committed. |

Node with native TypeScript, no build step, **no dependencies**, everything runs locally.
43 tests. Synthetic data throughout, and labelled as such.

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

---

### Before this

AML/KYC and banking operations — BNP Paribas, Société Générale, Viva Wallet, and a
fintech AML operation. At Société Générale I led five analysts and cut our false-positive
escalation rate by around 18 %.

That rate was never a metric on a slide. It was the size of the pile on my desk, and it
is why every tool here is built around what an automated decision costs the people who
have to live with it.

📍 Athens, relocating to New York · 🇫🇷 🇬🇧 · [LinkedIn](https://www.linkedin.com/in/arslane-chaouche-ramdane-95595a388/)
