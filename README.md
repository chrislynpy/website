# Articles

Each article is a `.json` file in this folder. The website loads them automatically on page load.

## How to add a new article

Create a new `.json` file with this structure:

```json
{
  "id": "art13",
  "cat": "garden",
  "catLabel": "Gardening",
  "icon": "🌾",
  "thumbClass": "thumb-moss",
  "title": "Your Article Title Here",
  "date": "Jun 2025",
  "readTime": "4 min read",
  "body": "<p>Your first paragraph.</p><h3>A subheading</h3><p>More content.</p><blockquote>A memorable quote.</blockquote>"
}
```

### Fields

| Field | Options | Description |
|---|---|---|
| `id` | any unique string | e.g. `art13`, used for linking |
| `cat` | `garden` / `business` / `tech` | controls which filter tab it appears under |
| `catLabel` | any string | display label e.g. `Gardening` |
| `icon` | any emoji | shown as the article thumbnail |
| `thumbClass` | `thumb-moss` / `thumb-terra` / `thumb-slate` | background colour of thumbnail |
| `title` | string | article headline |
| `date` | string | e.g. `Jun 2025` |
| `readTime` | string | e.g. `5 min read` |
| `body` | HTML string | full article content — use `<p>`, `<h3>`, `<blockquote>` |

### Body HTML tags supported
- `<p>` — paragraph
- `<h3>` — subheading
- `<blockquote>` — pull quote (styled with terracotta left border)

### Naming convention
`{category}-{short-slug}.json` — e.g. `garden-composting-hdb.json`

Articles are sorted by the order they appear in `articles-index.json`. Update that file when you add a new article.

---

## articles-index.json

This file controls the **order** articles appear on the site and which ones show in the "Featured" section on the home page.

```json
{
  "featured": ["art1", "art5", "art9", "art2"],
  "order": ["art1", "art2", "art3", "art4", "art5", "art6", "art7", "art8", "art9", "art10", "art11", "art12"]
}
```
