# 🎭 Alternate Story Extravaganza — Hub

> Every script becomes a branching universe. Pick your path. Shape your ending.

A GitHub-hosted hub for interactive branching story e-books. Each story is generated from a raw script — narrated, written, or transcribed — and turned into a dark-theme single-file HTML experience with **10 scenes**, **4 choices each**, and **4+ distinct endings**.

---

## 🚀 Live Stories

| Story | Genre | Scenes | Status |
|-------|-------|--------|--------|
| [The Quiet Inheritance](stories/marcus-jenkins.html) | Drama | 10 | ✅ Live |

---

## 📁 Project Structure

```
alternate-story-hub/
├── index.html              ← The hub homepage (story gallery)
├── src/
│   └── generator.html      ← AI-powered story generator (paste script → get HTML)
├── stories/
│   └── marcus-jenkins.html ← Published story files go here
├── scripts/
│   └── script-01-marcus-jenkins.txt  ← Raw source scripts (for reference)
└── docs/
    └── adding-a-story.md   ← Step-by-step guide
```

---

## ✨ How to Add a New Story

### Step 1 — Prepare Your Script
- Any format works: timestamped transcript (`0:00 Text...`), plain prose, spoken word narration
- Minimum ~500 words for a rich story; 2,000–5,000 words is ideal
- Save it in `scripts/` for your records

### Step 2 — Run the Generator
1. Open `src/generator.html` in your browser
2. Enter your story **title** and select a **genre**
3. Paste your full script into the text box
4. Click **Generate Interactive Story**
5. Claude reads your script and builds the full branching HTML (takes ~30–60 seconds)

### Step 3 — Download & Save
- Click **Download HTML**
- Save the file to `stories/your-story-slug.html`

### Step 4 — Add a Card to the Hub
Open `index.html` and find the `<!-- Story Card -->` comment. Copy an existing `.card` block and update:

```html
<div class="card">
  <div class="card-accent-bar"></div>
  <div class="card-body">
    <div class="card-meta">
      <span class="tag tag-drama">Drama</span>   <!-- change genre -->
      <span class="tag tag-scenes">10 Scenes</span>
    </div>
    <h3>Your Story Title</h3>
    <p>A 2–3 sentence teaser for your story...</p>
  </div>
  <div class="card-footer">
    <div class="card-stats">
      <span class="cs"><strong>4</strong> Endings</span>
      <span class="cs"><strong>~35 min</strong> read</span>
    </div>
    <a href="stories/your-story-slug.html" class="btn btn-primary read-btn">Read Story</a>
  </div>
</div>
```

Also update the story count stat at the top of `index.html`:
```html
<span class="stat-num" id="storyCount">2</span>  <!-- increment this -->
```

### Step 5 — Push to GitHub
```bash
git add stories/your-story-slug.html scripts/your-script.txt index.html
git commit -m "Add story: Your Story Title"
git push
```

**That's it.** Your story is live on the hub. 🎉

---

## 🌐 Hosting on GitHub Pages

1. Go to your repo **Settings → Pages**
2. Set source to `main` branch, root `/`
3. Your hub URL: `https://YOUR_USERNAME.github.io/alternate-story-hub/`

---

## 🎨 Story Card Genre Tags

Use these CSS classes for genre tags on cards in `index.html`:

| Genre | CSS Class |
|-------|-----------|
| Drama | `tag-drama` |
| Thriller | `tag-thriller` |
| Romance | `tag-romance` |
| Sci-Fi | `tag-scifi` |
| Mystery | `tag-mystery` |
| Comedy | `tag-comedy` |
| Add more in `index.html` style block as needed |

---

## 🔧 Generator Notes

The `src/generator.html` file calls the **Anthropic Claude API** to generate stories. It uses Claude Sonnet 4 and generates:
- 10 scenes (configurable to 6 or 8)
- 4 choices per scene
- Full branching prose derived from your source script
- Self-contained dark-theme HTML (no external dependencies)
- Keyboard navigation (1–4 for choices, R to restart)

The generator works directly in your browser — no server needed.

---

## 📖 Story Format

Each generated story HTML file is completely self-contained:
- No CDN dependencies
- No external fonts (uses system stacks)
- Works offline once downloaded
- ~1,000–1,800 lines of HTML/CSS/JS

---

*Built with Claude · Dark theme · Interactive branching fiction*
