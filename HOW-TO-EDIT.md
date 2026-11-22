# Your website: launch and editing guide

Everything here happens in your web browser on github.com. No code, no installs.

---

## Part 1: Put the site online (one time, about 20 minutes)

1. **Create a free GitHub account** at github.com.
2. **Create a repository.** Click **+** (top right) → **New repository**.
   - Name it exactly: `YOUR-USERNAME.github.io` (use your real GitHub username).
   - Set it to **Public** and click **Create repository**.
3. **Upload the site files.** On the new repository page, click **uploading an existing file**.
   Unzip the site folder on your computer, open it, select **everything inside it**
   (including the folders that start with `_`), and drag it all into the browser.
   Click **Commit changes**.
   - On a Mac, files starting with `_` are visible; files starting with `.` are hidden, and that's fine.
4. **Turn on GitHub Pages.** Go to **Settings** → **Pages**. Under **Build and deployment**,
   choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
5. Wait one to two minutes, then visit `https://YOUR-USERNAME.github.io`. Your site is live.

## Part 2: Use your own domain (optional, about $12 a year)

1. **Buy a domain** such as `heathersubba.com` from Cloudflare, Namecheap, or Squarespace Domains.
2. In GitHub, go to **Settings** → **Pages** → **Custom domain**, type your domain, and click **Save**.
3. At the company where you bought the domain, open its **DNS settings** and add:
   - Four **A** records for `@` pointing to:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One **CNAME** record for `www` pointing to `YOUR-USERNAME.github.io`
4. Back in **Settings** → **Pages**, check **Enforce HTTPS** once it becomes available
   (this can take up to a day).

---

## Part 3: Editing your site

**How every edit works:** open the file on github.com → click the **pencil icon** →
make your change → click **Commit changes**. The site updates in about a minute.

### Add a book, article, or management note

Open the matching file in the `_data` folder:

| To add… | Edit this file |
|---|---|
| A book recommendation | `_data/books.yml` |
| An article | `_data/articles.yml` |
| A management idea | `_data/management_notes.yml` |
| A project, event, or course | `_data/projects.yml` |

Each file has an example at the top. Copy it, remove the `# ` at the start of each
line, and fill it in. A finished book entry looks like this:

```yaml
- title: "The Making of a Manager"
  author: "Julie Zhuo"
  topic: "Leadership"
  note: "The best first-year manager guide I've read."
```

Put your newest entry at the top. The top three books also appear on your home page.
Sections with no entries stay hidden until you add one.

### Publish an essay

1. Open the `_drafts` folder. There's a starter draft called `the-self-service-myth.md`
   with writing prompts in it. Drafts don't appear on the site.
2. When it's ready, go to the main page of your repository and click
   **Add file** → **Create new file**. In the name box, type the folder and a name
   that starts with the date, like:
   `_posts/2026-12-15-the-self-service-myth.md`
   (Typing `_posts/` creates the folder if it isn't there yet.)
3. Paste in your essay, keeping the top section between the `---` lines:

```markdown
---
title: The self-service myth in AI education
summary: One sentence that tells readers what this essay argues.
---

Your essay starts here. Leave a blank line between paragraphs.

## A subheading looks like this

- A bullet point looks like this
```

### Edit a case study

Open the `_case_studies` folder and click the one you want. The top section
(between the `---` lines) holds the title, summary, and result numbers. Everything
below it is the write-up.

To change the order they appear in, change the `order:` numbers.

### Add your resume

1. Export your resume from Google Docs as a PDF (**File** → **Download** → **PDF**).
2. Open the `assets` folder → **Add file** → **Upload files**, and upload it.
   Name it something like `Heather-Subba-Resume.pdf`.
3. Open `_config.yml` and change the resume line to:
   `resume: "/assets/Heather-Subba-Resume.pdf"`

A **Resume** link then appears in the menu.

### Change your intro, email, or LinkedIn

- Home page text: `index.html` (edit the sentences between the `<p>` tags)
- Email, LinkedIn, and site description: `_config.yml`

---

## If something breaks

The most common cause is spacing in a `.yml` file. Every line of an entry must line
up exactly like the example, using spaces (not tabs). If your text contains a colon,
wrap it in quotes.

To see whether an update worked, open the **Actions** tab in your repository. A green
check means it's live. A red X means something needs fixing. Click it to see which
file caused the problem, or ask Claude to help.
