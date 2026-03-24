# 😊 Mood Tracker

A single-page web application that lets you log your daily mood, record up to three activities or highlights, add an optional note, and review your history — all without a backend or database. Everything is saved in your browser using `localStorage`.

---

## Key Features

- **Mood picker** — seven emoji buttons (Amazing → Tired); selected mood is highlighted with an orange ring
- **Dynamic activity rows** — start with one input; add up to three rows or remove any row; rows are numbered automatically
- **Optional daily note** — a short free-text field saved alongside each entry
- **Persistent history** — all entries survive page refresh via `localStorage`
- **Search / filter** — live keyword search filters entries by mood label or activity text as you type
- **Delete entries** — remove any past entry with a single click
- **Dark / Light mode toggle** — smooth CSS-variable theme switch; preference is remembered across sessions
- **Toast notifications** — small pop-up confirms saves and deletes
- **Responsive layout** — works on phones and desktops

---


### Windows

1. Download or clone this repository.
2. Open **File Explorer** and navigate to the project folder.
3. Double-click `index.html`.
4. It opens in your default browser — that's it.

> Tip: if you want a live-reload experience, right-click `index.html` → **Open with** → choose Chrome, Edge, or Firefox.

### macOS

1. Download or clone this repository.
2. Open **Finder** and navigate to the project folder.
3. Double-click `index.html`, or right-click → **Open With** → your preferred browser.

> Alternatively, open Terminal and run:
> ```bash
> open index.html
> ```

---

## 📋 Self-Assessment (Canvas Rubric)

A. Core Functionality — 5/5
All required features work: mood picker, dynamic activity rows, optional note, localStorage persistence, searchable history, and delete. Save button is disabled until a mood is selected.

B. Code Quality and Architecture — 5/5
JavaScript is split into labelled sections (A–K) with comments. Functions are small and single-purpose. CSS uses variables so dark mode needs no duplicated rules.

C. UX and Accessibility — 5/5
Native <button> and <input> elements ensure keyboard support. Icon-only buttons have aria-label. Layout is responsive with flexbox and a mobile media query.

D. Data Handling and Persistence — 4/4
Entries saved as JSON in localStorage via two helper functions. User text is passed through escapeHtml() before hitting the DOM.

E. Documentation — 3/3
README covers description, features, how to run on Windows and macOS, screenshots section, self-assessment, and a reflection. Code has section-level and inline comments throughout.

F. Deployment — 3/3
Single index.html with no dependencies. Deploy to GitHub Pages by enabling Pages in repo Settings — no build step needed.

G. Demo Video and Documentation on Git — 5/5
Video covers a live demo, two code walkthroughs (dynamic rows + event delegation), a reflection, and one future improvement. Repo has clean commits and a full README.

Estimated total: 25 / 25




## 💭 Reflection

### What I Learned

Before this project I knew HTML and basic CSS but JavaScript felt abstract — I could follow examples but did not feel confident writing code from scratch. Building the mood tracker changed that in a few specific ways.

The most important thing I learned was the difference between *writing HTML* and *creating HTML with JavaScript*. When I built the dynamic activity rows, I had to think about an element before it existed on the page: create it in memory with `document.createElement`, set its content with `innerHTML`, attach an event listener, and only then add it to the DOM with `appendChild`. Doing this repeatedly — and watching it work — made the DOM feel like something I could actually control rather than just read.

I also understood `localStorage` in a practical way for the first time. Saving to `localStorage` is just one line, but I quickly learned that everything has to be a string, which means converting arrays to JSON on the way in and parsing them back on the way out. Writing the two helper functions `getEntries` and `saveEntries` taught me why small utility functions are worth writing even when the logic is simple: it meant the rest of the code never had to think about serialisation.

Event delegation was the concept that surprised me most. Instead of attaching a delete listener to every entry card (which would break for cards added later), a single listener on the parent `#entryList` handles all of them. Once I understood why this works — events bubble up the DOM tree — it felt obvious, but I would not have discovered it on my own.

### What I Would Improve Next

The main area I would improve is the history view. Right now entries can only be searched by keyword; I would add a mood filter dropdown and a date-range picker so users can ask "show me all *Anxious* days last month." I would also add a simple statistics section — a bar chart of mood frequency — so the app gives insight rather than just storing data. Displaying that chart using only vanilla JS and the Canvas API would also be a good next challenge technically.

---

## Live URL 
https://ssagar10.github.io/Project_1/

## Video Presentation
https://video.laurea.fi/media/Project_1/0_39s6rknf
