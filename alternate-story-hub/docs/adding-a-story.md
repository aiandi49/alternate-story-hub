# Adding a New Story — Step-by-Step Guide

## Before You Start

You need:
- A script (any length, any format)
- A browser (Chrome or Firefox work best)
- GitHub access to push your changes

---

## Step 1: Write or Collect Your Script

Scripts can be:
- **Transcripts** from narrated videos (timestamped format like `0:00 Text here...`)  
- **Written prose** — your own original short story or draft
- **Dictated narratives** — spoken word converted to text via any transcription tool

Save your raw script to `scripts/` in this format:
```
script-NN-your-story-title.txt
```
Example: `script-02-the-forgotten-heir.txt`

Aim for **1,000–5,000 words** for the richest branching story. Shorter scripts still work but produce more concise scenes.

---

## Step 2: Open the Generator

Open this file in your browser:
```
src/generator.html
```

*(Double-click it in Finder/Explorer, or serve it locally — it works as a standalone file.)*

---

## Step 3: Fill in the Form

| Field | What to Enter |
|-------|--------------|
| **Story Title** | The display title (e.g., "The Forgotten Heir") |
| **Genre Tag** | Pick from the dropdown — shown as a badge on the hub card |
| **Scenes** | 10 recommended; 8 for shorter scripts; 6 for very short |
| **Script** | Paste your full script text |

---

## Step 4: Generate

Click **Generate Interactive Story**.

The generator will:
1. Send your script + instructions to Claude
2. Wait for Claude to write all scenes (~30–90 seconds)
3. Show a log of progress
4. Display a success message when done

---

## Step 5: Download and Preview

- Click **Preview Story** to read it in a new tab before saving
- Click **Download HTML** to save the file
- Rename if needed, then move to `stories/your-slug.html`

**Naming convention:** lowercase, hyphens, no spaces  
Example: `the-forgotten-heir.html`

---

## Step 6: Add a Hub Card

Open `index.html`. Find the story grid section (look for `<!-- Story Card -->`).

Copy this block and paste it **before** the `card-add` placeholder:

```html
<div class="card">
  <div class="card-accent-bar"></div>
  <div class="card-body">
    <div class="card-meta">
      <span class="tag tag-drama">Drama</span>
      <span class="tag tag-scenes">10 Scenes</span>
    </div>
    <h3>The Forgotten Heir</h3>
    <p>
      A 2–3 sentence teaser that hooks the reader. What's the core tension?
      What choice does the main character face? Keep it intriguing.
    </p>
  </div>
  <div class="card-footer">
    <div class="card-stats">
      <span class="cs"><strong>4</strong> Endings</span>
      <span class="cs"><strong>~30 min</strong> read</span>
    </div>
    <a href="stories/the-forgotten-heir.html" class="btn btn-primary read-btn">Read Story</a>
  </div>
</div>
```

Customize:
- Genre tag class and label
- `h3` title
- `p` teaser text
- `href` pointing to your new file
- Estimated read time (10 scenes × ~3 min = ~30 min is typical)

---

## Step 7: Update the Story Count

Near the top of `index.html`, find:
```html
<span class="stat-num" id="storyCount">1</span>
```
Increment the number by 1.

---

## Step 8: Commit and Push

```bash
git add stories/the-forgotten-heir.html
git add scripts/script-02-the-forgotten-heir.txt
git add index.html
git commit -m "Add story: The Forgotten Heir"
git push origin main
```

Your story will be live on GitHub Pages within ~30 seconds. ✅

---

## Tips

- **Regenerate if needed**: If the first generation doesn't feel right, paste the script again with a more specific title or adjust the genre — Claude reads context well.
- **Edit the HTML directly**: The generated story files are clean, readable HTML. You can open them in any text editor and tweak scene text, add lines, or adjust choices.
- **Teaser text matters**: The 2–3 sentence description on the hub card is what gets people to click. Make it punchy.
- **Consistent slugs**: Use the same slug for the HTML file and any reference to it so links don't break.
