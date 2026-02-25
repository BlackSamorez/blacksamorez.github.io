---
description: Convert an arXiv paper into a concise blog post with images
---

# arXiv to Blog Post Workflow

This workflow automatically converts an arXiv link into a fully fleshed-out blog post on this Hugo site, downloading metadata, formatting a concise article, and extracting source images.

// turbo-all

## Execution Steps

1. **Read Abstract and Metadata:**
   - Use the `read_url_content` tool on the provided arXiv abs link. Extract the title, abstract, authors, and any GitHub links.

2. **Draft the Blog Post Draft:**
   - Generate a slug from the title.
   - Create the directory `content/post/<slug>/` and write an `index.md` file inside it.
   - Use Hugo frontmatter with `title`, `date` (current date), `summary`, `authors` (usually `["admin"]`), and relevant `tags`.
   - Write a concise post with punchy headers, highlighting the core problem, key observations, and results.
   - Append links to the paper and code.
   - Add a small disclaimer at the bottom:
     `---`
     `*Disclaimer: This blog post was automatically generated from the [arXiv paper](<arxiv_link>).*`

3. **Download and Unpack arXiv Source:**
   - Replace `/abs/` with `/e-print/` in the arXiv URL to get the source tarball.
   - Run a bash command to download and extract the paper's source:
   ```bash
   mkdir -p .arxiv_temp && cd .arxiv_temp
   curl -sSL -o source.tar.gz <ARXIV_EPRINT_URL>
   tar -xzf source.tar.gz
   ```

4. **Convert Figures from PDF to PNG:**
   - Locate the figures from the extracted LaTeX source (typically inside `data/figures/`, `figures/`, or the root directory).
   - Use macOS's built-in `sips` command to convert the identified PDF images to PNG and output them directly into the newly created post directory.
   ```bash
   # Example:
   sips -s format png .arxiv_temp/data/figures/figure1.pdf --out content/post/<slug>/figure1.png
   # Complete this for a few of the most relevant figures found.
   ```

5. **Insert Images into the Post:**
   - Embed the converted `.png` images into the blog post `index.md` document at the most logical insertion points (e.g. `![Figure 1 Description](figure1.png)`). Edit the file using file content editing tools.

6. **Cleanup Workspace:**
   - Remove the temporary extraction directory.
   ```bash
   rm -rf .arxiv_temp
   ```

7. **Verify the final post:**
   - Check the local Hugo server (e.g., `http://localhost:1313/post/<slug>/`) to ensure everything renders smoothly.
