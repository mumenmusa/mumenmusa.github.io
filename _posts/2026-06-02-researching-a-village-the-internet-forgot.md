---
title: "Researching a village the internet forgot"
date: 2026-06-02 09:00:00 -0700
---

There is a village north of Ramallah called Turmus Ayya. My family is from there. Wikipedia gives it a handful of paragraphs and the usual census stub. I wanted more — not for a paper, not for a project, just for myself. So I sat down one evening with a language model and asked it to help me dig.

What follows is the process. Not the conclusions — the conclusions are in [the full report](#) — the process. The process is the part I think is worth writing down.

## The first prompt

I told the model what village I was looking for, gave it three spelling variants, and added one clause that turned out to matter more than anything else in the rest of the conversation:

> Even if it has information about other villages around that might reference it, or at least relatively or very closely mentions it.

That single instruction is what turned up *Turbasaim* — a Crusader-Latin form of the name that I had never seen in any of the modern sources. *Turbasaim* doesn't appear in Wikipedia. It doesn't appear in the village's own profile pages. It shows up in a nineteenth-century Palestine Exploration Fund nomenclature study that itself was reading thirteenth-century church cartularies. The name had been sitting in a footnote for a hundred and forty years.

I asked the model where it found it. It pointed me at Röhricht's *Regesta Regni Hierosolymitani*, the registry of medieval Crusader-era charters. The 1145 entry says half the income of *Turbasaim* and a nearby place called *Dere* was granted to the Abbey of Mount Tabor, to support the church at Sinjil — the next village over from where my grandparents lived.

That is a real fact about my family's village, surfaced because I added a clause about spelling variations and adjacent places. I would not have found it any other way.

## The matching problem

The reason a clause like that matters: this is a place whose name has been written in Arabic, Ottoman Turkish, Latinized Crusader French, nineteenth-century English, nineteenth-century German, and modern transliterations that don't agree with each other. The British Mandate's own census officials wrote in 1931 that the transliteration system they were using was already being abandoned, *while the census was still going to press*.

If you search for "Turmus Ayya" you find the modern village. If you search for "Turmus 'Aiya" you find the 1931 census. If you search for "Tourmous'aya" you find a French art-history article about a Roman sarcophagus. If you search for "Turbasaim" you find a 1145 land grant.

These are all the same place. None of them link to each other.

## What I learned about prompting

A few things crystallized over the course of the research that I want to remember.

**Ask for the negative result.** The single most valuable thing the model surfaced wasn't a confirmation, it was a contradiction. Some twentieth-century scholars proposed that Turmus Ayya was the ancient *Tur Shimon* mentioned in rabbinic sources. The model found a Boaz Zissu paper arguing against that identification — on the grounds that surface survey at the village had produced potsherds from several periods *but none from the Hellenistic period*. That negative finding is the kind of thing a casual search will never give you, because nobody writes a Wikipedia paragraph about an identification that didn't hold up.

**Source classes matter more than source counts.** I told the model to prioritize in roughly this order: official censuses, primary historical publications, explorer/survey literature, archaeology, and only then secondary compilations or local profiles. The reason is that local profiles tend to silently compress together primary facts, antiquarian conjectures, and oral etymologies. Without explicit ranking, the model treats them all as equally citeable. With ranking, it tells you when it's reaching for the bottom of the stack.

**Filter your false positives early.** Two categories of garbage results plagued every search: there is another place called *Tall al-Turmus* in Gaza, which is not the same village; and *turmus* in Arabic also means *lupini beans*, which dominate the search results for anything resembling the name. Telling the model these two patterns existed before it started cut the noise in half.

**Push deeper on the thread that surprises you.** When *Turbasaim* came back, I didn't move on to the next question. I spent the next several turns just on Crusader cartularies. That follow-up gave me the names *Dere*, *Deir el-Fikia*, and *Ras ad-Deir* — a cluster of small ecclesiastical sites adjacent to my village that I now suspect were economically linked to it eight hundred years ago. The diminishing returns on a single thread come much later than you expect.

## What it got wrong

It is not a perfect collaborator.

It conflated dates more than once. An English-language summary called the village's famous Roman sarcophagus "2nd century B.C.", and a separate German art-history catalog dated the same object to 240–250 CE. The model initially reported both as if they were consistent. I had to push it to flag the discrepancy. When I did, it correctly noted that one source was a popular retelling and the other was specialist cataloging — but it didn't volunteer that distinction on its own.

It occasionally over-anchored on the most-cited claim. The diaspora statistic — that something like 80 percent of Turmus Ayya residents hold U.S. citizenship — appears in dozens of journalistic sources but in zero official ones. The model repeated it confidently several times before I asked where the underlying data came from. There is no underlying data. It is a journalistic estimate that has self-replicated.

It is bad at adjudicating what *can't be known*. Some questions — the exact pre-Roman name of the site, the genealogy of specific families before the nineteenth century — have answers that simply don't exist in any accessible archive. The model wants to give you an answer. You have to actively push back and ask it to enumerate the limits of the evidence, not just summarize the evidence.

## The shape of the final report

The output of all of this is a 24-page comprehensive report covering name etymology, medieval cartulary evidence, Ottoman tax records, Mandate-era censuses, nineteenth-century explorer accounts, archaeological surveys, family lineages, twentieth-century migration patterns, and the contemporary record of settler violence. It includes a source-comparison table and a timeline.

I don't think the report is the interesting artifact. I think the *transcript* of the research session is. The report tells you what is known about Turmus Ayya. The transcript tells you how I got from "I want to know more about my family's village" to "here is a 1145 land grant naming it." That second thing is reproducible. The first is just an output.

## What I'd do differently next time

Three things.

1. **Start with the negative-result prompt earlier.** Asking "what identifications for this place have *failed*, and why?" should be one of the first questions, not one of the last. It calibrates everything that follows.

2. **Build the variant table before doing any searches.** I had to back-fill the name-variant table after I'd already done a lot of single-spelling searches. Future-me should treat the variant table as a precondition: list every form, every script, every spelling convention, before issuing a single query.

3. **Ask for the source class of every claim, every time.** Not "is this true," but "what kind of source is this." Census versus survey versus secondary compilation versus folk etymology. The four categories require four different levels of trust, and the model will assign all four the same confidence if you don't make it differentiate.

---

This is the first post on this blog. I want to write more like it — research notes, builds, things I'm working through. Mostly for future-me. The next one is probably about Obsidian, six years in.

If you have your own deep-research project — a hometown, a family name, an ancestor, a forgotten place — I'd encourage you to try this. The internet hasn't forgotten the things you think it has. It has just filed them under names you don't know yet.
