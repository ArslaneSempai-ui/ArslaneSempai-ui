# Your retrieval benchmark is not yours

*What I measured building a document search engine for compliance, and what it cost to find out.*

Arslane Chaouche Ramdane — August 2026

---

Every vendor deck for document search quotes an accuracy figure. Ninety-something percent,
on a public benchmark, against a corpus you will never see. The figure is usually true. It
is also close to useless for deciding whether the thing will work on your procedures, and
the reasons why are measurable rather than philosophical.

I built one — a retrieval engine over compliance documents, with the refusal behaviour a
regulated function actually needs — and measured it twice, on two different corpora, with
an evaluation set written before the engine existed. What follows is what only appears once
you measure on your own documents.

## The ranking of methods flips between corpora

On a technical documentation corpus, the same three methods gave **inverted** results
against the compliance one: keywords level with embeddings, fusion of the two winning, and an
optimal chunk size twice as large. Same code, different documents, opposite conclusion.

It is worse than that, and I only found out by re-measuring. On the first compliance corpus,
embeddings beat keyword search on first-position accuracy — 75 % [53–89] against 31 % [15–52],
intervals disjoint, an ordering I was willing to defend. Re-run on the set the tool ships with
today, the same comparison gives 68 % [46–85] against 37 % [19–59]. Embeddings still lead every
row. **But the intervals now overlap, so the ordering is no longer established** — not because
the engine got worse, but because the questions changed underneath a result I had already
written down.

What transfers between corpora is the method — how you measure. Not the settings, and not
the ranking. Anyone quoting you their numbers without having seen your documents is selling
you someone else's result.

## At twenty questions, most comparisons are noise

That is the second lesson, and it is arithmetic rather than opinion. Twenty evaluation
questions put roughly **±18 points** around any percentage drawn from them; nineteen put a
little more. At that width, three engines separated by twenty or thirty points cannot be
ranked at all — every interval in the current table overlaps every other. Reading an ordering
off it anyway is reading noise as signal.

This matters because twenty is already more than most internal evaluations do. If a
comparison is presented to you without a sample size and an interval, the honest reading is
that the difference has not been established. That is not pedantry: it is the difference
between "version B is better" and "version B was luckier this time", and only one of those
is worth a migration budget.

## The threshold is a business decision, not a technical one

An index always returns a nearest neighbour. It cannot come back empty. So "I don't know"
is not something retrieval produces — it is something you decide, by putting a bar under
which the system stays silent. Where you put it is a trade, and it can be priced:

| Bar | Correct first | Correctly refused | Silent in error | **Invented** |
|---|---|---|---|---|
| 0.70 | 63.2 % | 0 of 6 | 6 | **6** |
| 0.82 | 57.9 % | 3 of 6 | 6 | **3** |
| **<!--p:rag.barre~n2-->0.84<!--/p-->** | 52.6 % | **6 of 6** | 5 | **0** |
| 0.86 | 36.8 % | 6 of 6 | 10 | 0 |

Read the last column first. Below <!--p:rag.barre~n2-->0.84<!--/p--> the system starts answering questions the corpus
cannot answer — in compliance, that is the expensive failure, because a confident wrong
answer about a filing deadline is worse than no answer at all. Above it, retrieval
collapses and the silence becomes indiscriminate.

The five questions it stays silent on at <!--p:rag.barre~n2-->0.84<!--/p--> are the price of buying zero inventions. And
the useful finding is that **moving the bar does not buy them back**: at 0.82 there are
still six silent errors, plus three inventions. That cost needs better retrieval, not a
different threshold. A vendor tuning a number in front of you is not fixing it.

## The failures live below the model, in the plumbing

Three of the most expensive problems had nothing to do with the model:

**Extraction.** One PDF page arrived as a single 500-word passage, because extraction lost
the paragraph breaks and everything came back on one line. A passage that long dilutes
whatever it contains and ranks for nothing.

**Cover slides.** "Market Risk Fundamentals — Course Introduction" ranked as highly for a
French question about reporting deadlines as for a question about apple pie. Short and
generic, it weakly resembles everything.

**Scores are not comparable in absolute terms.** On one corpus every similarity score sat
between 0.806 and 0.849, and the correct passage ranked fourth — 0.007 behind the first.
Any pipeline that fuses methods by score rather than by rank is adding noise on that corpus.

None of these appear in a benchmark score. All of them decide whether the system is usable.

## Multilinguality is asymmetric

A French question found its answer in an English document. The reverse did not hold: asked
in English against a French manual, the same question scored 0.813 and matched the wrong
document, where its French phrasing scored 0.902.

Measuring one direction tells you nothing about the other. If your documents are in one
language and your analysts ask in another, that is the case to test, and it is the one
demonstrations skip.

## What to ask before signing

1. **On our documents, or on yours?** Any number produced on a public corpus is a statement
   about that corpus.
2. **How many evaluation questions, and what interval?** Under fifty, most differences are
   not establishable. Ask for the interval, not the point.
3. **What does it do when the answer is not there?** Ask for the refusal rate and the cost
   of it, in both directions — invented answers and unjustified silences.
4. **Who writes the evaluation set, and when?** Questions written after seeing the system's
   output measure the system's habits, not its usefulness. Ours were written first.
5. **What does the extraction do to our worst PDF?** Not the clean one.

## What this does not prove

The compliance corpus is synthetic and labelled as such — real regulation, cited, with
invented internal procedure around it. The evaluation sets are 20 and <!--p:rag.questions-->25<!--/p--> questions, which is
small, and every figure here is reported with that in mind. One engine, two corpora, one
domain. The refusal counts are counts, not rates: <!--p:rag.sansReponsePossible-->6<!--/p--> correctly refused questions put a
95 % interval of [61–100] around any percentage you draw from them.

It was also tested on five real PDFs — <!--p:ragReel.pages-->312<!--/p--> pages of bank risk reports and course material,
<!--p:ragReel.passages-->618<!--/p--> passages indexed in <!--p:ragReel.secondesIndexation-->14<!--/p--> seconds, no unreadable file. That is a load figure, not a
quality one.

What I would defend is narrower than a benchmark and more useful: the method is
transferable, the numbers are not, and the two most consequential decisions in a retrieval
system — where the silence threshold sits, and what the extraction does to your documents —
are invisible to every accuracy figure you will be shown.

---

*The engine, the evaluation sets, and every figure above:
[compliance-document-search](https://github.com/ArslaneSempai-ui/compliance-document-search) —
runs in the browser, no upload.*
