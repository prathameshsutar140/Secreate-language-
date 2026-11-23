# Binary Secret Language

A responsive, browser-based encoder and decoder with two distinct formats.

## Features
- Universal UTF-8 binary encoding/decoding for Unicode, emoji, symbols and multilingual text.
- Custom 5-bit alphabet: A=00001 through Z=11010; `/` separates words.
- Emoji and symbol insertion panel.
- Copy, download, swap, sample, theme toggle and local conversion history.
- No build tools, external dependencies, account or server required.

## Run
Open `index.html` in a modern browser. For best clipboard behavior, serve the folder locally:
- Python: `python -m http.server 8000`
- Then open `http://localhost:8000`

## Format notes
UTF-8 mode writes each byte as 8 bits, with a space between bytes. Remove whitespace before decoding; the decoder also accepts whitespace. It validates byte alignment and UTF-8 validity.

Custom 5-bit mode is intentionally limited to English A-Z and spaces. It does not encode emoji or punctuation. Use Universal UTF-8 for those characters. The 5-bit format is a reversible encoding, not encryption.

## Storage and privacy
History is stored in this browser's localStorage on the current device. It is not uploaded to a server. Clearing browser site data may erase it.
