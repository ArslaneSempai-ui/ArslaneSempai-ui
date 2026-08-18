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
| **[alert-triage-economics](https://github.com/ArslaneSempai-ui/alert-triage-economics)** | Seven analysts of eight are paid to handle nothing, and the next true positive is **free** down to threshold <!--p:economics.seuilGratuitLePlusLarge~n2-->0.45<!--/p--> — after which it costs <!--p:economics.premierCasPayant~usd-->$32,476<!--/p--> | The cost is bought in steps, not units. Funding part of a step buys nothing — not less, nothing. |
| **[process-cycle-time](https://github.com/ArslaneSempai-ui/process-cycle-time)** | <!--p:cycle.joursDeBoutEnBout~n1-->6.4<!--/p--> days end to end, of which **<!--p:cycle.heuresTravaillees~n1-->2.3<!--/p--> hours** of actual work. <!--p:cycle.routesDistinctes-->74<!--/p--> distinct routes through a process that documents one | The mean describes no case: clean files finish in 2.4 days, twice-returned ones take 21.6. A target set on the mean is met by every case that never had a problem. |
| **[funnel-economics](https://github.com/ArslaneSempai-ui/funnel-economics)** | The biggest leak is **not** the best place to spend: <!--p:funnel.meilleurRendement~x1-->31.1×<!--/p--> against <!--p:funnel.pireRendement~x1-->2.1×<!--/p--> per dollar | And the ranking is not stable. "The signup page has already been rebuilt twice" is the most ordinary of four scenarios, and it moves signup from first place to third. |
| **[kyc-triage-agent](https://github.com/ArslaneSempai-ui/kyc-triage-agent)** | <!--p:triage.partAutomatisee~pc0-->58 %<!--/p--> of files decided without a human and **zero** uncontrolled onboardings, on <!--p:triage.dossiers-->400<!--/p--> cases | The threshold was inert: <!--p:triage.escaladesParLaRegle-->111<!--/p--> of the escalations come from a rule that is certain, and no threshold will move those. |
| **[regression-bench](https://github.com/ArslaneSempai-ui/regression-bench)** | Across three deterministic versions, <!--p:banc.passesAuDebut-->13<!--/p--> → <!--p:banc.passesALaFin-->19<!--/p--> of <!--p:banc.cas-->22<!--/p--> cases — and the third **breaks two** while its score rises | A rising pass rate is not an improvement. The fourth races a clock, so it gets a range and not a score: publishing a single number would be publishing a draw. |
| **[remediation-backlog](https://github.com/ArslaneSempai-ui/remediation-backlog)** | Taking the worst finding first misses <!--p:remediation.manquesReflexe-->3<!--/p--> of <!--p:remediation.constats-->8<!--/p--> deadlines and costs **<!--p:remediation.coutReflexe~usd-->$695,000<!--/p-->**; the identical work sorted by deadline misses none | Same team, same effort — only the order changes. And counting red lines is not counting money: an order can miss more deadlines and cost a third as much. |
| **[drift-monitor](https://github.com/ArslaneSempai-ui/drift-monitor)** | Every model-risk note alarms at PSI <!--p:derive.seuilDeLaNote~n1-->0.2<!--/p-->. A <!--p:derive.deplacement~n1-->0.3<!--/p-->σ shift moves the index to **<!--p:derive.signal~n2-->0.09<!--/p-->** | The alarm sits above the signal it exists to see. Below <!--p:derive.fenetreSeparante-->350<!--/p--> observations a check, no threshold separates noise from that shift at all. |
| **[cascade-routing](https://github.com/ArslaneSempai-ui/cascade-routing)** | Sending every field to the large model reaches <!--p:cascade.justesseGrandModele~n1-->80.5<!--/p--> % for <!--p:cascade.coutGrandModele~usd-->$800<!--/p-->; routing field by field reaches **<!--p:cascade.justesseOptimale~n1-->84.5<!--/p--> %** for **<!--p:cascade.coutOptimal~usd-->$180<!--/p-->** | Better and <!--p:cascade.facteur~x1-->4.4×<!--/p--> cheaper, because <!--p:cascade.champsGratuits-->3<!--/p--> of the 5 fields are carried by regexes that cost nothing. The tiers were measured on held-out records; the human tier and every price are assumed. |
| **[growth-versus-controls](https://github.com/ArslaneSempai-ui/growth-versus-controls)** | The A/B test settles the lift — **<!--p:arbitrage.ecartConversion~n1-->2.1<!--/p--> %** [<!--p:arbitrage.ecartBas~n2-->0.15<!--/p--> – <!--p:arbitrage.ecartHaut~n2-->4.04<!--/p-->] — and **not** the decision | The sign flips at an undetected-risk share of <!--p:arbitrage.bascule~n2-->1.33<!--/p--> %, inside the range both functions are prepared to defend. A larger test cannot settle that; measuring the share can. |
| **[compliance-document-search](https://github.com/ArslaneSempai-ui/compliance-document-search)** | On <!--p:rag.questions-->25<!--/p--> questions: <!--p:rag.justes-->10<!--/p--> right, <!--p:rag.ratees-->9<!--/p--> wrong, and **<!--p:rag.silencesJustifies-->6<!--/p--> times it said nothing** — every time no answer existed | The two populations overlap and the bar sits inside the overlap. No position separates them; each one trades silences against inventions. |

**Written up:** [Your retrieval benchmark is not yours](benchmarks-are-not-yours.md) — what I
measured building the search engine, why the ranking of methods flips between corpora, and the
five questions to ask a vendor before signing.

Node with native TypeScript, no build step, **no runtime dependencies**, everything runs
locally. **<!--p:portfolio.tests-->236<!--/p--> tests.** Synthetic data throughout and labelled as such; the regulation is
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

📍 New York · 🇫🇷 🇬🇧 · [LinkedIn](https://www.linkedin.com/in/arslane-chaouche-ramdane-95595a388/)
