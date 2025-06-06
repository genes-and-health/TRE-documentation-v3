
# How to Update this Documentation

Welcome! This page is part of the documentation itself — and serves as your guide for contributing updates to it.

The documentation is built using [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/), a powerful and customisable static site generator for project documentation. Whether you’re fixing typos, updating content, or adding entirely new sections, this guide will walk you through how to do it cleanly and effectively.

!!! tip
    You should expect that when editing the documentation, the MkDocs server is already running in the background, so any changes you make will be reflected live as you save the files.

---

## ✅ Prerequisites

Before you get started:

- You must have **write access** to the project root and its documentation folder (`docs/`).
- You must be able to edit or add images under `docs/images/`.
- **You do _not_ need to branch or fork**. This documentation encourages **low-friction updates** — just edit the files directly if you have access.
- If multiple people are working on documentation simultaneously, consider coordinating to avoid merge conflicts.

---

## ✏️ Updating Existing Pages

All content lives in Markdown (`.md`) files within the `docs/` directory.

### Steps:

1. Open the relevant Markdown file inside `docs/` (or a subdirectory).
2. Edit the content using any text editor (e.g., VS Code).
3. Save your changes — the MkDocs live server will reload automatically.
4. Check formatting and visual layout locally.
5. Commit when you're happy with the result.

#### Example: Adding an info box

Material for MkDocs supports [admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/):

```markdown
!!! note
    You can add callouts like this to draw attention.
```

Which renders as:

!!! note
    You can add callouts like this to draw attention.

---

## 🖼️ Adding Images

All image assets should live under the `docs/images/` folder.

### How to include images:

1. Copy your image file (e.g., `cool-manhattan-plot.png`) to `docs/images/`. Or a subfolder therein (e.g. `docs/images/regenie/`)
2. Embed it in your `.md` file like so:

   ```markdown
   ![Cool Manhattan Plot](images/cool-manhattan-plot.png)
   ```

Images will automatically scale in most cases, but you can use Markdown extensions like `:width:` if needed (with proper plugin support).

---

## 🆕 Creating New Pages

Want to add a new topic or guide?

### 1. Create a new file

Place your new Markdown file into an appropriate location, such as:

```bash
docs/[my-new-documentation-feature]/integration.md
```

You can use an existing page as a template for structure and formatting.

### 2. Add to Navigation

Edit the `mkdocs.yml` file at the root of this project to include your new page at the appropriate location in the site `nav`:

```yaml
nav:
  - Home: index.md
  - Developer Guide:
      - Integration: developer-guide/integration.md
```

YAML is whitespace-sensitive — use 2 spaces per indentation, not tabs!

!!! info
    If you don’t add your page to `mkdocs.yml`, it won’t appear in the sidebar navigation.

---

## 🧩 Markdown Extensions and Best Practices

Material for MkDocs includes several powerful extensions:

- **Admonitions**: `!!! note`, `!!! warning`, `!!! example`, etc.
- **Code syntax highlighting**:

Here’s some syntax highlighting to display python:
  ```python
  def greet(name):
      print(f"Hello, {name}")
  ```
- **Internal linking**:
  ```markdown
  [Read the Getting Started Guide](getting-started.md)
  ```

Use these features to make your contributions clearer and more engaging.

---

## 🔒 Permissions

You’ll need access to the following:

- `docs/` – for Markdown pages
- `docs/images/` – for images and diagrams
- `mkdocs.yml` – to update navigation structure

If you're missing access, contact a maintainer or administrator.

---

## ✅ Final Checklist Before Committing

- [ ] Proofread for spelling and grammar
- [ ] Image paths and links verified
- [ ] New pages added to `nav` in `mkdocs.yml`
- [ ] Content renders correctly in local preview
- [ ] Used relevant MkDocs features (admonitions, syntax highlighting, etc.)

---

## 🛠️ Additional Resources

- [Material for MkDocs documentation](https://squidfunk.github.io/mkdocs-material/)
- [MkDocs User Guide](https://www.mkdocs.org/user-guide/)
- [Markdown Syntax Guide](https://www.markdownguide.org/basic-syntax/)

---

## 🧵 Need Help?

Open a ticket, check the `README.md`, or reach out in the internal documentation channel.

Happy writing!

## STU WOZ HERE
