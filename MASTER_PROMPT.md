# Master Prompt — Binary Secret Language Encoder & Decoder

Build a professional, production-quality responsive web application named **Binary Secret Language**.

## Goal
Create a polished text-to-binary and binary-to-text tool with two clearly separated formats:
1. **Custom 5-bit Alphabet Mode** — A=00001 through Z=11010; letters are concatenated without spaces and `/` is the only word separator. Decode by splitting each word into exact 5-bit groups. Reject malformed groups and unsupported characters with clear errors.
2. **Universal UTF-8 Binary Mode** — Encode the UTF-8 bytes of any Unicode string as 8-bit binary groups separated by spaces. Support all Unicode characters available in the browser, including uppercase/lowercase letters, digits, whitespace, punctuation, mathematical symbols, currency symbols, emoji, skin-tone modifiers, flags, ZWJ emoji sequences, Hindi, Marathi and other scripts. Decode by validating groups and reconstructing bytes with a strict UTF-8 decoder. Preserve the original text exactly.

## Required interface
- Premium responsive dashboard with a refined dark theme, subtle gradients, glass-like cards, accessible contrast and a light-theme toggle.
- Clear mode selector, input and output text areas, Encode, Decode, Swap, Clear, Copy, Download TXT and Save History actions.
- Character counters and visible status/error messages.
- Searchable or categorized emoji/symbol picker that inserts characters at the cursor without corrupting Unicode.
- Example button showing text containing emoji, symbols, non-English script and numbers.
- Recent history with load and clear controls.
- Keyboard accessibility, semantic HTML, focus indicators, responsive mobile layout and reduced-motion support.

## Technical requirements
- Use HTML5, CSS3 and vanilla JavaScript; no framework required.
- Use `TextEncoder` and `TextDecoder('utf-8', { fatal: true })` for UTF-8 conversion.
- Treat UTF-8 as bytes, not JavaScript UTF-16 code units. Never split surrogate pairs or grapheme sequences manually.
- Strict validation: UTF-8 input must contain only 0/1 and permitted whitespace, and total bit count must be divisible by 8. Custom input must contain only 0/1 and `/`, with each word's bit count divisible by 5 and each value in 1–26.
- Do not silently discard unsupported characters or invalid data.
- Store history locally using IndexedDB (preferred) or localStorage, with a clear-history action. Explain local storage behavior.
- No external API calls and no server upload for message content.
- Add comments for core conversion functions and a README with run instructions, format specifications, limitations and privacy notes.

## Important product distinction
Encoding is not encryption. Clearly explain that binary conversion does not protect confidentiality. Do not claim that the custom 5-bit format supports emoji or symbols; those are handled by Universal UTF-8 mode. If secure encryption is added later, implement it as a separate, explicitly labeled feature using established browser cryptography APIs and authenticated encryption.

## Acceptance tests
- UTF-8 round-trip exactly preserves `Hello 😀 ❤️ — नमस्ते! ₹100 + 25%`.
- UTF-8 round-trip preserves newline, tab, emoji with modifiers, flags and combined emoji sequences.
- ASCII A encodes to `01000001`; UTF-8 emoji bytes are emitted as 8-bit groups.
- Custom mode maps A to `00001`, Z to `11010`, and `HI` to `0100001001`.
- Custom `GOOD MORNING` encodes to `00111011110111100100/01101011111001001110010010111000111`.
- Invalid UTF-8 bit lengths and invalid custom 5-bit groups produce useful errors.
- Copy, download, history, theme and mobile layout work without console errors.

Deliver the complete runnable source project, README, and concise setup instructions. Do not provide mock buttons or pretend that a feature works when it does not.