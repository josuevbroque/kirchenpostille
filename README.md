# Luther's Church Postil: daily reader

A static website that opens to Martin Luther's sermon for the current day of
the church year and presents it as a paged reader.

## What it is

Martin Luther's *Church Postil* is a collection of sermons on the appointed
Gospel and Epistle readings for each Sunday and festival. This site shows the
sermon for today's date. Pages turn like a book, and the accent colour and
background glow follow the liturgical season.

**Source text:** Martin Luther's Church Postil, *The Complete Lenker Edition in
One Volume*. The text is Luther's own, in John Nicholas Lenker's translation
of over a century ago.

## Calendar

The site uses the old, historic one-year calendar and lectionary, not the
modern three-year cycle (Years A, B and C). The readings for a given Sunday
are the same every year. The seasons are Advent, Christmas, Epiphany,
Septuagesima and Lent, Easter, Pentecost, and the Sundays after Trinity.

- Easter is calculated for each year, and the movable days are worked out from it.
- If no sermon is assigned to a date, the sermon for the current church week is shown, with a note.
- Some days have several sermons (a Gospel and an Epistle sermon, for example). They are chosen from the menu.

## Features

- Opens on today's sermon. Any date can be linked with `?d=YYYY-MM-DD`.
- Paged reading by arrow buttons, the ← → keys, swiping, or tapping the page edges.
- Paragraph numbers and section headings always stay on the same page as their text.
- A menu with section jump, previous and next postil, text size, a calendar and a list of all days.
- A welcome panel on the first visit, reopened from the menu's About button.
- Works on phones and desktops.

## Files

```
index.html     the whole app (HTML, CSS and JavaScript in one file)
data/
  manifest.js  list of sermon files and the kind of each (Gospel/Epistle)
  <day>.js     one file per day of the church year (65 files), loaded on demand
```

## Running it

Open `index.html` in a browser, or upload the folder to any static host
(GitHub Pages, Netlify, and so on). Keep `index.html` and the `data` folder
together. The fonts (Newsreader and Inter) load from Google Fonts. Without a
connection the site falls back to Georgia and the system sans-serif.

## Changing it

- **Glow strength:** edit the `.glow` rule in the `<style>` block of `index.html`. The `.21` values set the corner strength and `.021` sets the overall tint.
- **Season colours:** the `COL` table and the `setColor` function in the script.
- **Adding or editing a sermon:** each `data/<day>.js` file is a list of
  `{title, kind, paras}`. Paragraphs starting with `## ` are section headings,
  `> ` is Scripture, and `[n]` marks a numbered paragraph.

## Privacy

The site stores only the text-size setting and a "welcome seen" flag in the
visitor's own browser. It collects no data.
