# How to Update this Documentation

Welcome! This page is part of the documentation itself — and serves as your guide for contributing updates to it.

The documentation is built using [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/), a powerful and customisable static site generator for project documentation. Whether you’re fixing typos, updating content, or adding entirely new sections, this guide will walk you through how to do it cleanly and effectively.

!!! tip
    You should expect that when editing the documentation, the MkDocs server is already running in the background, so any changes you make will be reflected live as you save the files.

---

## ✅ Prerequisites

Before you get started:

- You must have **write access** to the [test-docs](https://github.com/genes-and-health/test-docs) repository on GitHub.
- **You do _not_ need to branch or fork**. This documentation encourages **low-friction updates** — just edit the files directly if you have access.
- If multiple people are working on documentation simultaneously, consider coordinating to avoid merge conflicts.

---

## ✏️ Updating Existing Pages

All content lives in Markdown (`.md`) files within the `docs/` directory.

### Steps:

1. In [test-docs](https://genes-and-health.github.io/test-docs), navigate to the documentation page you want to update.
2. Click the :material-file-edit-outline:{.md-typeset} icon in the top right of the page.
3. If prompted, sign in as a user with write access to the `test-docs` GitHub repo.
4. You are now in edit mode (editing the .md file for that documentation page).
5. Commit changes… when you are happy with the edits you have made.

!!! tip
    Return to the page in the documentation where the changes were made. Wait a few seconds and then refresh the page in the browser. The changes should appear in place. 
<!--
1. Open the relevant Markdown file inside `docs/` (or a subdirectory).
2. Edit the content using any text editor (e.g., VS Code).
3. Save your changes — the MkDocs live server will reload automatically.
4. Check formatting and visual layout locally.
5. Commit when you're happy with the result.
-->



---

## 🖼️ Adding Images

All image assets should live under the `docs/images/` folder of the `test-docs` repo. If an image for use exists elsewhere on the internet then (provided you have permission) make a copy and place it in `docs/images/`. This protects against referring in the docs to an image which has subsequently been moved or deleted externally. 

### How to include images:

1. Upload your image file (e.g., `cool-manhattan-plot.png`) to `docs/images/` in the `test-docs` repo. Or a subfolder therein (e.g. `docs/images/regenie/`)
2. refer to the image in your `.md` file like so:

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

- **Callout boxes**: `!!! note`, `!!! warning`, `!!! example`, etc.

### Example: Adding a `note` box

Material for MkDocs calls these [admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/):

```markdown
!!! note
    You can add callouts like this to draw attention.
```

Which renders as:

!!! note
    You can add callouts like this to draw attention.
- **Code syntax highlighting**:

Here’s how to display some python with syntax highlighting:

````markdown
```python
def greet(name: pl.Utf8) -> None:
  print(f"Hello, {name}")
```
````

Which appears in the documentation as:

```python
def greet(name: pl.Utf8) -> None:
    print(f"Hello, {name}")
```

<!--
Another example:
```cobol
IDENTIFICATION DIVISION.
PROGRAM-ID. GREET.

DATA DIVISION.
WORKING-STORAGE SECTION.
01 USER-NAME        PIC X(100).
01 GREETING-MSG     PIC X(120).

PROCEDURE DIVISION.
MAIN-LOGIC.
DISPLAY "Enter your name: ".
  ACCEPT USER-NAME
  STRING "Hello, " DELIMITED BY SIZE
      USER-NAME DELIMITED BY SPACE
      INTO GREETING-MSG
  DISPLAY GREETING-MSG
  STOP RUN.
```
-->

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
