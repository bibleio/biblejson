![banner](https://github.com/user-attachments/assets/34cd22a2-7751-4e24-9f2a-24b66a007362)

BibleJSON is a new universal formatting standard for putting biblical texts into JSON.

# `converter`

Right now, you are able to convert [eBible.org](https://ebible.org) Bible `.htm` files into BibleJSON, with our converter script written in Rust. Soon, we plan to add support for other file formats.

## Usage

- Get source code from the repo
- Get some HTML content from [eBible.org](https://ebible.org), and put it in some directory. (pick a translation, and download the "Zipped mobile HTML" option!
- Then run `cargo run path/to/html`

# Format

Soon we plan to move documentation to dev.bibleio.com. Here's a summary of the format of BibleJSON:

- `details`
    - `bibleAbbrev` - the abbreviation of the translation that the file is, ex. “BSB”
    - `bibleName` - the name of the translation, ex “Berean Standard Bible”
    - `bookAbbrev` - the short ID of the book that the file is, ex “JHN”
    - `bookName` - the name of the book, ex “John”
    - `chapter` - the chapter number
- `content` - the actual Bible content
    - item - each item is a JSON object literal
        - `type` - the type of the item - `header` | `subheader` | `verse` | `verseQuote` | `whitespace`
        - `verse` (only type `verse` ) - the verse number
        - `text` - array of the text
            - could be either a normal string
            - or an object literal with extra formatting
                - `content` - the content string
                - modifier - boolean - the modifier that the formatting is - `italic` | `red`

# Feedback and contributing

Please give feedback on the format, before we decide to deploy it everywhere accross Bibleio. We need feedback on developer experience on actually using it within apps, websites, etc.

If you could help make a converter script for another file format, that would be amazing!

[Discord]() - or `bibleio@bibleio.com`

Licensed `MIT-0`. No attribution required.