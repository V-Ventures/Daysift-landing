# Daysift Blog Writing Guide

How we write. Distilled from close reading of Proton's blog (voice/privacy) and
TechCrunch/Forbes (human tech prose), plus the V-Ventures house copy rules.
Goal: articles that read as written by a person who knows the subject and will
be held to the claim. Never robotic, never AI-slop.

## The lede (first 1-2 sentences)
- Start with a fact, a scene, or a tension. Never "In today's fast-paced world"
  or "In this article we'll explore."
- Two families that work:
  - **Fact/tension:** "Daysift keeps your browsing history on your device. The
    AI feature was the one part that didn't."
  - **Scene:** a specific, small human moment before you zoom out.
- Put the actual thesis (nut graf) in paragraph 2-3, in one clear sentence.

## Voice
- First person plural: "we built," "we moved," "we think." Never a disembodied
  brand voice.
- Possessive, pointed at the reader: "your history," "your queries," not "the
  data" or "user information."
- Name the adversary plainly when relevant (Big Tech monetising your data,
  US-jurisdiction AI providers) before you name the fix.
- State what we DON'T do as a feature: "not trained on, not logged, not kept."
- Humility as a trust signal: "we can't see it," "even we can't."
- Close calm: restate the why in one sentence, then ONE low-pressure CTA. No
  hard sell, no stacked CTAs.

## Sentence craft
- Vary length hard. A three-word sentence next to a forty-word one. Read aloud;
  if every sentence is 18-22 words, rewrite.
- Active voice. The subject does the thing.
- Have a point of view. Commit. "This matters because X," not "some might argue."
- Specificity beats abstraction every time. Real numbers, real names, real
  dates. "≈400 installs, peaked at 100+ weekly" beats "growing user base."

## Handling privacy/security claims (the most important rule)
Copy Proton's discipline: every claim is **scoped to a boundary**, never a
floating "we protect your privacy."
- Say what data we don't collect, what we can't see, and what's still true in a
  worst case — and say plainly **where the protection stops**.
- Pair every privacy claim with either a plain analogy OR the specific mechanism.
- Use "open-weight models," never "open source AI."
- For the Proton integration specifically: over the Lumo **API** it is HTTPS/TLS
  and Proton's no-logs/no-training policy — it is **NOT** end-to-end or
  zero-access encrypted (those are the Lumo app). The text also passes through
  Daysift's own proxy. Say this plainly. Honesty here is on-brand and builds trust.

## Kill on sight (AI tells)
- Openers: "In today's fast-paced world", "In the ever-evolving landscape".
- Hedge padding: "it's worth noting", "it's important to remember", "arguably".
- Empty transitions at paragraph starts: "Furthermore", "Moreover", "Additionally".
- Uniform sentence length; listy sameness (everything a 3-5 item bullet list).
- Em-dash overuse. Use sparingly, for one sharp interruption.
- Hype: "revolutionary", "game-changing", "seamless", "robust", "leverage".
- Fake balance with no verdict; summary-of-a-summary conclusions; explaining the
  irony instead of letting it sit.

## Structure
- Explainer skeleton: plain definition → why it matters (stakes) → how it works
  (analogy + mechanism) → concrete example → how Daysift does it (scoped claims)
  → one-paragraph close + single CTA.
- Headers are plain noun phrases or the question a reader would type into search.
  Not clever wordplay.
- End forward, not backward: a next step, an honest open question, or the
  sharpest concrete detail. Never a recap of the intro.
- Length: 1,200-2,200 words for most posts. Don't pad.

## Images (see IMAGES note)
- No AI-generated slop. Use our own product renders (headless-Chrome shots of
  `landing/screenshots/index.html` / `screenshots.html` frames) for product
  visuals, and real Unsplash photos (with attribution) for human/conceptual shots.
- Keep to what earns its place; Proton uses images sparingly.

_Source research: Proton blog (13 posts) + TechCrunch/Forbes (9 pieces), 2026-09-30._
</content>
