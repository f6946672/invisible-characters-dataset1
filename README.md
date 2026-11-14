# Invisible Characters Dataset

A verified, machine-readable list of Unicode's invisible, zero-width, blank and format characters — codepoint, official name, category, HTML entity and notes — maintained alongside the tools at [stripinvisible.com](https://stripinvisible.com).

## What counts as "invisible"?

Some Unicode characters paint no ink at all (zero-width spaces, format marks, tag characters). Others paint nothing but still take up room (Hangul fillers, the Braille blank, exotic spaces), so a field can look empty while being full. A third group steers the text around it without showing itself: bidirectional controls, variation selectors, joiners. All three kinds end up pasted into usernames, documents, code and AI prompts — usually by accident, sometimes on purpose. This dataset lists the ones that matter in practice: **412 codepoints**, every name and category checked against the Unicode Character Database (via Python `unicodedata`, Unicode 15.0).

## Use the tools online

The dataset is the reference behind these free tools on stripinvisible.com — no uploads, everything runs in the browser:

- [Invisible text checker](https://stripinvisible.com/invisible-text) — see which characters in your text paint nothing, and how wide they really are
- [Hidden characters finder](https://stripinvisible.com/hidden-characters) — scan text and locate every hidden character, with positions
- [Invisible characters list](https://stripinvisible.com/invisible-characters) — the human-readable version of this dataset, with copy buttons
- [Empty character generator](https://stripinvisible.com/empty-character) — copy blank characters for empty-looking names and messages
- [Tag characters decoder](https://stripinvisible.com/tag-characters) — reveal ASCII text hidden inside tag characters
- [Zero width space](https://stripinvisible.com/zero-width-space) and [zero width joiner](https://stripinvisible.com/zero-width-joiner) — copy and remove U+200B / U+200D
- [Line separators](https://stripinvisible.com/line-separators) — the U+2028 / U+2029 parsing traps, measured
- Cleaners: [Word](https://stripinvisible.com/clean-word), [JSON](https://stripinvisible.com/clean-json), [Excel](https://stripinvisible.com/clean-excel) — strip invisible characters out of pasted text

## The data

| Character | Codepoint | Unicode name | Category | HTML entity | Notes |
|---|---|---|---|---|---|
| ` ` | U+0020 | SPACE | Zs | &#x20; | The ordinary space. Every other entry in this dataset is measured against it; several of the exotic spaces below fold back to it under NFKC normalization. |
| ` ` | U+00A0 | NO-BREAK SPACE | Zs | &#xA0; (&nbsp;) | A space that will not break a line. The one people paste by accident most often. |
| `­` | U+00AD | SOFT HYPHEN | Cf | &#xAD; (&shy;) | Marks where a word may break. Only becomes visible if the line actually breaks there. |
| `͏` | U+034F | COMBINING GRAPHEME JOINER | Mn | &#x34F; | Ties two characters together so they behave as one grapheme. |
| `؜` | U+061C | ARABIC LETTER MARK | Cf | &#x61C; | Bidirectional mark used with Arabic script. |
| `ᅟ` | U+115F | HANGUL CHOSEONG FILLER | Lo | &#x115F; | Hangul filler with the advance width of a full syllable block and no ink (0 px painted, 16 px advance in the site's measurements). Used for blank-looking usernames and nicknames. |
| `ᅠ` | U+1160 | HANGUL JUNGSEONG FILLER | Lo | &#x1160; | Hangul filler with the advance width of a full syllable block and no ink (0 px painted, 16 px advance in the site's measurements). Used for blank-looking usernames and nicknames. |
| `᠋` | U+180B | MONGOLIAN FREE VARIATION SELECTOR ONE | Mn | &#x180B; | Select a glyph shape in Mongolian. |
| `᠌` | U+180C | MONGOLIAN FREE VARIATION SELECTOR TWO | Mn | &#x180C; | Select a glyph shape in Mongolian. |
| `᠍` | U+180D | MONGOLIAN FREE VARIATION SELECTOR THREE | Mn | &#x180D; | Select a glyph shape in Mongolian. |
| `᠎` | U+180E | MONGOLIAN VOWEL SEPARATOR | Cf | &#x180E; | A Mongolian separator that renders as nothing in most fonts. Classed as a space (Zs) before Unicode 6.3 moved it to format (Cf); many cleanup patterns still miss it. |
| ` ` | U+2000 | EN QUAD | Zs | &#x2000; | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+2001 | EM QUAD | Zs | &#x2001; | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+2002 | EN SPACE | Zs | &#x2002; (&ensp;) | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+2003 | EM SPACE | Zs | &#x2003; (&emsp;) | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+2004 | THREE-PER-EM SPACE | Zs | &#x2004; (&emsp13;) | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+2005 | FOUR-PER-EM SPACE | Zs | &#x2005; (&emsp14;) | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+2006 | SIX-PER-EM SPACE | Zs | &#x2006; | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+2007 | FIGURE SPACE | Zs | &#x2007; (&numsp;) | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+2008 | PUNCTUATION SPACE | Zs | &#x2008; (&puncsp;) | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+2009 | THIN SPACE | Zs | &#x2009; (&thinsp;) | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| ` ` | U+200A | HAIR SPACE | Zs | &#x200A; (&hairsp;) | One of the eleven fixed-width spaces, U+2000-U+200A, running from EN QUAD down to HAIR SPACE. |
| `​` | U+200B | ZERO WIDTH SPACE | Cf | &#x200B; (&ZeroWidthSpace;) | Lets a browser break a long word. Invisible, survives copy and paste, and the most common hidden character there is. |
| `‌` | U+200C | ZERO WIDTH NON-JOINER | Cf | &#x200C; (&zwnj;) | Stops a join. Required for correct Persian, Arabic and Devanagari text. |
| `‍` | U+200D | ZERO WIDTH JOINER | Cf | &#x200D; (&zwj;) | Joins characters. This is what holds an emoji family together as one picture. |
| `‎` | U+200E | LEFT-TO-RIGHT MARK | Cf | &#x200E; (&lrm;) | Forces left-to-right direction for the characters after it. |
| `‏` | U+200F | RIGHT-TO-LEFT MARK | Cf | &#x200F; (&rlm;) | Forces right-to-left direction for the characters after it. |
| ` ` | U+2028 | LINE SEPARATOR | Zl | &#x2028; | A line break that is not a newline character. Modern JSON parsers accept it, but older parsers and strict string handling still trip on it. |
| ` ` | U+2029 | PARAGRAPH SEPARATOR | Zp | &#x2029; | A paragraph break that is not a newline character. Same parsing caveat as U+2028. |
| `‪` | U+202A | LEFT-TO-RIGHT EMBEDDING | Cf | &#x202A; | One of the five bidi embedding/override characters that set text direction. Safe to delete only in matched pairs. |
| `‫` | U+202B | RIGHT-TO-LEFT EMBEDDING | Cf | &#x202B; | One of the five bidi embedding/override characters that set text direction. Safe to delete only in matched pairs. |
| `‬` | U+202C | POP DIRECTIONAL FORMATTING | Cf | &#x202C; | One of the five bidi embedding/override characters that set text direction. Safe to delete only in matched pairs. |
| `‭` | U+202D | LEFT-TO-RIGHT OVERRIDE | Cf | &#x202D; | One of the five bidi embedding/override characters that set text direction. Safe to delete only in matched pairs. |
| `‮` | U+202E | RIGHT-TO-LEFT OVERRIDE | Cf | &#x202E; | One of the five bidi embedding/override characters that set text direction. Safe to delete only in matched pairs. |
| ` ` | U+202F | NARROW NO-BREAK SPACE | Zs | &#x202F; | A thin unbreakable space, used before units and currency in French typography. |
| ` ` | U+205F | MEDIUM MATHEMATICAL SPACE | Zs | &#x205F; (&MediumSpace;) | A medium space for use inside formulas. |
| `⁠` | U+2060 | WORD JOINER | Cf | &#x2060; (&NoBreak;) | Stops a line break between two words without drawing anything. |
| `⁡` | U+2061 | FUNCTION APPLICATION | Cf | &#x2061; (&af;) | An invisible function-application operator, meaningful only inside mathematical notation. |
| `⁢` | U+2062 | INVISIBLE TIMES | Cf | &#x2062; (&it;) | An invisible multiplication operator, meaningful only inside mathematical notation. |
| `⁣` | U+2063 | INVISIBLE SEPARATOR | Cf | &#x2063; (&ic;) | An invisible separator (as in a long number grouped without commas), meaningful only inside mathematical notation. |
| `⁤` | U+2064 | INVISIBLE PLUS | Cf | &#x2064; | An invisible addition operator, meaningful only inside mathematical notation. |
| `⁦` | U+2066 | LEFT-TO-RIGHT ISOLATE | Cf | &#x2066; | One of the four bidi isolate characters that isolate a run of text from its surroundings. |
| `⁧` | U+2067 | RIGHT-TO-LEFT ISOLATE | Cf | &#x2067; | One of the four bidi isolate characters that isolate a run of text from its surroundings. |
| `⁨` | U+2068 | FIRST STRONG ISOLATE | Cf | &#x2068; | One of the four bidi isolate characters that isolate a run of text from its surroundings. |
| `⁩` | U+2069 | POP DIRECTIONAL ISOLATE | Cf | &#x2069; | One of the four bidi isolate characters that isolate a run of text from its surroundings. |
| `⁪` | U+206A | INHIBIT SYMMETRIC SWAPPING | Cf | &#x206A; | Deprecated format control, retained for legacy text. Renders as nothing. |
| `⁫` | U+206B | ACTIVATE SYMMETRIC SWAPPING | Cf | &#x206B; | Deprecated format control, retained for legacy text. Renders as nothing. |
| `⁬` | U+206C | INHIBIT ARABIC FORM SHAPING | Cf | &#x206C; | Deprecated format control, retained for legacy text. Renders as nothing. |
| `⁭` | U+206D | ACTIVATE ARABIC FORM SHAPING | Cf | &#x206D; | Deprecated format control, retained for legacy text. Renders as nothing. |
| `⁮` | U+206E | NATIONAL DIGIT SHAPES | Cf | &#x206E; | Deprecated format control, retained for legacy text. Renders as nothing. |
| `⁯` | U+206F | NOMINAL DIGIT SHAPES | Cf | &#x206F; | Deprecated format control, retained for legacy text. Renders as nothing. |
| `⠀` | U+2800 | BRAILLE PATTERN BLANK | So | &#x2800; | A Braille cell with no dots raised. Paints nothing but takes real width (about 10.4 px in the site's measurements), so it survives filters that strip zero-width characters. |
| `　` | U+3000 | IDEOGRAPHIC SPACE | Zs | &#x3000; | A full-width space that matches the width of a CJK character. |
| `ㅤ` | U+3164 | HANGUL FILLER | Lo | &#x3164; | Hangul filler: a full-width blank. The site's tests show it folding to U+1160 under NFKC while surviving trim and strip. |
| `︀` | U+FE00 | VARIATION SELECTOR-1 | Mn | &#xFE00; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︁` | U+FE01 | VARIATION SELECTOR-2 | Mn | &#xFE01; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︂` | U+FE02 | VARIATION SELECTOR-3 | Mn | &#xFE02; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︃` | U+FE03 | VARIATION SELECTOR-4 | Mn | &#xFE03; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︄` | U+FE04 | VARIATION SELECTOR-5 | Mn | &#xFE04; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︅` | U+FE05 | VARIATION SELECTOR-6 | Mn | &#xFE05; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︆` | U+FE06 | VARIATION SELECTOR-7 | Mn | &#xFE06; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︇` | U+FE07 | VARIATION SELECTOR-8 | Mn | &#xFE07; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︈` | U+FE08 | VARIATION SELECTOR-9 | Mn | &#xFE08; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︉` | U+FE09 | VARIATION SELECTOR-10 | Mn | &#xFE09; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︊` | U+FE0A | VARIATION SELECTOR-11 | Mn | &#xFE0A; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︋` | U+FE0B | VARIATION SELECTOR-12 | Mn | &#xFE0B; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︌` | U+FE0C | VARIATION SELECTOR-13 | Mn | &#xFE0C; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︍` | U+FE0D | VARIATION SELECTOR-14 | Mn | &#xFE0D; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `︎` | U+FE0E | VARIATION SELECTOR-15 | Mn | &#xFE0E; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `️` | U+FE0F | VARIATION SELECTOR-16 | Mn | &#xFE0F; | Variation selector: follows a character and picks an alternate glyph form. Selector 16 (U+FE0F) is what keeps an emoji looking like an emoji. |
| `﻿` | U+FEFF | ZERO WIDTH NO-BREAK SPACE | Cf | &#xFEFF; | A byte order mark at the start of a file. Invisible and unwanted anywhere else. |
| `ﾠ` | U+FFA0 | HALFWIDTH HANGUL FILLER | Lo | &#xFFA0; | Halfwidth Hangul filler (0 px painted, 8 px advance in the site's measurements). Used for blank-looking nicknames. |
| `￹` | U+FFF9 | INTERLINEAR ANNOTATION ANCHOR | Cf | &#xFFF9; | Starts an interlinear (ruby-style) annotation run. Rarely intended in plain text. |
| `￺` | U+FFFA | INTERLINEAR ANNOTATION SEPARATOR | Cf | &#xFFFA; | Separates an interlinear annotation from its base text. Rarely intended in plain text. |
| `￻` | U+FFFB | INTERLINEAR ANNOTATION TERMINATOR | Cf | &#xFFFB; | Ends an interlinear annotation run. Rarely intended in plain text. |
| `󠀁` | U+E0001 | LANGUAGE TAG | Cf | &#xE0001; | Part of the tag character block, used to label language inside a string. |
| _(96 chars)_ | U+E0020–U+E007F | TAG CHARACTERS | Cf | — | 96 characters that mirror printable ASCII and spell out hidden text inside a string; used to fingerprint copied output. **Every codepoint is listed individually in the data files.** |
| _(240 chars)_ | U+E0100–U+E01EF | VARIATION SELECTOR SUPPLEMENT | Mn | — | More glyph variants, mostly for CJK ideographs. **Every codepoint is listed individually in the data files.** |

### Also flagged by the tools, but not rows in this dataset

The Private Use ranges — **U+E000–U+F8FF**, **U+F0000–U+FFFFD** and **U+100000–U+10FFFD** — have no official names and no assigned meaning; they exist for private agreements. In copied text they are nearly always tracking marks or watermarks, so stripinvisible's checker flags them, but listing thousands of unassigned codepoints as "characters" would be inventing data. They are therefore documented here as ranges only.

## Common uses and pitfalls

- **Blank usernames and nicknames.** Hangul fillers (U+115F, U+1160, U+3164, U+FFA0) and the Braille blank (U+2800) make a name that looks empty but isn't. Platforms that only trim ASCII whitespace let them through.
- **The usual cleanup pattern misses half the list.** A `\p{C}` sweep catches the Cf format characters but not the fillers (category Lo), the exotic spaces (Zs), or the separators (Zl/Zp). Those families survive most "remove invisible characters" snippets.
- **Hidden text in prompts and copied output.** Tag characters (U+E0020–U+E007F) encode a second, invisible ASCII string inside visible text. The same trick fingerprints copied documents: zero-width characters sprinkled through a text identify which copy leaked.
- **Token cost.** Invisible characters are not free in LLM APIs: every one is tokenized and billed like a visible character, and a block of them can cost more than the sentence carrying it. (Measured examples: [stripinvisible.com/token-cost](https://stripinvisible.com/token-cost).)
- **Parsers and file formats.** U+2028 and U+2029 are line/paragraph breaks that aren't newlines; modern JSON parsers accept them unescaped, older ones and strict string handling still break. U+FEFF mid-file is an invisible glitch that survives most editors.
- **Don't strip blindly.** U+200C (ZWNJ) is required for correct Persian, Arabic and Devanagari; U+200D (ZWJ) is what holds emoji sequences — and some real letters in Indic scripts — together. Removing them corrupts legitimate text.
- **Bidirectional controls are a security smell.** U+202A–U+202E and the isolates can make displayed text order differ from logical order (the trick behind "Trojan Source"-style spoofing). In source code or filenames, treat them as hostile until proven otherwise.

## Data files

Same data, three formats:

- [`data/invisible-characters.json`](data/invisible-characters.json) — array of objects
- [`data/invisible-characters.csv`](data/invisible-characters.csv) — flat table, UTF-8
- The table above — identical content, except the two large ranges (tag characters, variation selectors supplement) are condensed to one row each; the files list every codepoint individually.

Fields: `character` (the character itself), `codepoint` (e.g. `U+200B`), `unicode_name`, `category` (Unicode general category), `group`, `html_entity` (numeric hex reference), `named_entity` (HTML named entity, where one exists), `notes`.

Download the files from this repository (clone it, or open a file and use the raw/download button), or read them straight from the raw URLs once published.

## How this data was verified

The character set and plain-English notes come from the pages and tools of [stripinvisible.com](https://stripinvisible.com), where each character is exercised in a working checker. Every Unicode name and general category in the files was then re-checked programmatically against Python's `unicodedata` (Unicode 15.0); where a casual site description and the standard disagreed, the standard won. Measured claims in the notes (painted width, NFKC behaviour, trim/strip behaviour) are the site's own published test results.

## License

The dataset (JSON, CSV and the table in this README) is released under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) — public domain, use it for anything. See [LICENSE](LICENSE). The Unicode character names and categories themselves are data from the Unicode Character Database.
