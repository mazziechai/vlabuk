# vlabuk

i was going to make a why do they call it oven joke but then realized that would be stupid ~evie

## Guide to editing `words.json`

Sonkap is free to edit this, or ask me (evie). I'll only edit it to move stuff out of the spreadsheet & for cleanup. Everyone else please go through #submit-a-word in Discord.

**Before committing** changes to the JSON please run `cargo run`! This will update `words.js` to reflect your changes & fetch any necessary fonts (should take ~15 seconds).

Properties that exist:

- **`word`.**
- **`def`:** The *short definition*, corresponding to the "concept" spreadsheet column for roots, "meaning" for compounds/freewords, and "function" for particles.
- **`etymology`:**
    - **`lang`:** Source language.
    - **`word`.** If the word has a Wiktionary entry, please put the form shown in the URL or at the top of the page.
    - **`urlform`:** For e.g. Klingon, where the URL of the word *qa'* is `https://klingon.wiki/Word/Ka-`.
- **`notes`.**

Root-specific:

- **`alignment`:** The place structure.
- **`type`:** One of the new ones that start with a capital letter.
- **`semantics`:** The semantic space.
- **`xo` and `ko`:** The new `def` this word has when suffixed with either. (For ease of JSing these fields don't start with hyphens.)

The "pat." column is unnecessary here as it can be found via `/[^aeiou]$/.test(word) ? "a" : "b"`.

Compound-specific: **`gloss`**.

Particle-specific: **`class`**, **`status`**.