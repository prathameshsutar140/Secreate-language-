# Binary Secret Language

<p align="center">
  <strong>Encode anything. Decode everything.</strong><br>
  A browser-based binary converter with a custom 5-bit alphabet and universal UTF-8 support.
</p>

<p align="center">
  <img alt="HTML5" src="https://img.shields.io/badge/HTML5-markup-orange?logo=html5&logoColor=white">
  <img alt="CSS3" src="https://img.shields.io/badge/CSS3-styling-blue?logo=css3&logoColor=white">
  <img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-vanilla-yellow?logo=javascript&logoColor=black">
  <img alt="No dependencies" src="https://img.shields.io/badge/dependencies-none-brightgreen">
</p>

**Binary Secret Language** converts readable text into binary and converts valid binary data back into text. It offers two different formats: a simple custom 5-bit A–Z code and a universal UTF-8 byte representation for Unicode text.

> **Important:** Binary encoding is a reversible representation, not encryption. It does not hide information or provide password protection.

## Features

- **Universal UTF-8 mode** — convert Unicode text into 8-bit binary byte groups.
- **Emoji and symbol support** — handle emoji, punctuation, currency signs, mathematical symbols and other Unicode characters in UTF-8 mode.
- **Multilingual text** — supports text in scripts such as Devanagari, as well as other Unicode scripts supported by the browser.
- **Custom 5-bit mode** — encode letters A–Z using values 1–26.
- **Encode and decode** — convert in either direction with input validation.
- **Emoji and symbol panel** — insert available characters directly into the input.
- **Copy and download** — copy the output or save it as a `.txt` file.
- **Conversion history** — save and reload recent conversions on the same browser.
- **Responsive interface** — layout adapts to desktop, tablet and mobile screens.
- **Dark and light themes** — switch the appearance from the interface.

## Encoding modes

### 1. Custom 5-bit alphabet

Each English letter is assigned a number from 1 to 26 and represented using five binary bits.

| Letter | Number | Binary |
|:--:|--:|:--:|
| A | 1 | `00001` |
| B | 2 | `00010` |
| C | 3 | `00011` |
| D | 4 | `00100` |
| E | 5 | `00101` |
| ... | ... | ... |
| Z | 26 | `11010` |

**Format rules**

- Each letter uses exactly five bits.
- Encoded letters are joined together without spaces.
- A forward slash `/` separates words.
- This mode accepts English letters A–Z and spaces. The current encoder converts lowercase input to uppercase, so original letter case is not preserved.
- Emoji, digits and punctuation are not supported in this mode. Use Universal UTF-8 for those characters.

**Example: `HI`**

```text
H = 01000
I = 01001

HI = 0100001001
```

**Example: `GOOD MORNING`**

```text
00111011110111100100/01101011111001001110010010111000111
```

### 2. Universal UTF-8 binary

Universal mode encodes the text as UTF-8 bytes. Each byte is displayed as an 8-bit binary group, with a space between groups.

This supports ordinary text, numbers, whitespace, punctuation, symbols, emoji and multilingual characters.

**Example: `A`**

```text
A → 01000001
```

**Example: `😀`**

```text
😀 → 11110000 10011111 10011000 10000000
```

The decoder joins the 8-bit groups back into bytes and validates the UTF-8 sequence before returning text. Keep all bits intact when copying a binary message.

## Getting started

No package installation or build step is required. The application runs in a modern browser.

### Option 1: Open directly

1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. Choose **Universal UTF-8** or **Custom 5-bit**.
4. Enter text and select **Encode**, or enter binary and select **Decode**.

### Option 2: Run a local web server

If Python is installed, open a terminal in the project folder and run:

```bash
python -m http.server 8000
```

Then visit:

```text
http://localhost:8000
```

## How to use

1. Select an encoding mode.
2. Type or paste text into the first box.
3. Select **Encode** to generate binary.
4. To reverse the conversion, paste binary into the input box and select **Decode**.
5. Use **Copy result** or **Download .txt** to keep the output.
6. Select **Save to history** to store a conversion in the current browser.

The **Example** button loads a sample for the selected mode. The character panel inserts an emoji or symbol at the current cursor position.

## Technology

- **HTML5** — page structure and controls.
- **CSS3** — responsive layout, themes and visual styling.
- **Vanilla JavaScript** — conversion logic and interface interactions.
- **TextEncoder / TextDecoder** — UTF-8 byte conversion and decoding.
- **LocalStorage** — saves conversion history in the browser.

There are no third-party JavaScript libraries or external API services required by the current implementation.

## Privacy and data storage

- Text conversion happens in the browser.
- Saved history uses the browser's `localStorage` on the current device.
- The current application does not upload messages to a cloud database.
- Clearing browser site data may remove saved history.
- Avoid entering confidential information on shared devices.

## Limitations

- Custom 5-bit mode is limited to A–Z and word separators. It converts lowercase letters to uppercase.
- Universal UTF-8 mode is the option for emoji, symbols, digits, punctuation and non-English text.
- Binary output can be long for emoji and other multi-byte characters.
- This project performs encoding and decoding; it is not a secure encryption tool.
- History is local to the browser and is not synchronized across devices.

## Roadmap

Potential future improvements:

- Searchable emoji and symbol library.
- Import and export conversion history.
- QR-code sharing for encoded messages.
- Optional password-based encryption as a separate feature.
- Automated tests for Unicode and malformed binary input.
- Installable Progressive Web App (PWA) support.

These are ideas for future development and are not claims about features currently implemented.

## Contributing

Suggestions, bug reports and improvements are welcome. If you find an issue, please open a GitHub issue with:
- A short description of the problem.
- The selected encoding mode.
- Example input (do not include private messages).
- Expected and actual results.

## Author

**Prathamesh Sutar**

- GitHub: [@prathameshsutar140](https://github.com/prathameshsutar140)
- Repository: [Binary Secret Language](https://github.com/prathameshsutar140/Secreate-language-)

---

<p align="center">Made to explore binary representation, Unicode and text conversion.</p>
