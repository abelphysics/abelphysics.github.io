# Abel's physics resources website

A plain HTML and CSS website for GitHub Pages. The page background is white. The top navigation has exactly two sections: **About** and **Resources**. About is the homepage.

## Website organization

The Resources section contains a **Physics Resources** folder with three topic folders: **General Relativity**, **Quantum Field Theory**, and **Quantum Gravity**. Each folder contains an `index.html` file, which is that folder's page.

| File | What it controls |
| --- | --- |
| `index.html` | Your About page and homepage. |
| `style.css` | The appearance of every page. |
| `resources/index.html` | The Resources page, linking to Physics Resources. |
| `resources/physics-resources/index.html` | The Physics Resources page, linking to the three topics. |
| `resources/physics-resources/general-relativity/index.html` | General Relativity resources. |
| `resources/physics-resources/quantum-field-theory/index.html` | Quantum Field Theory resources. |
| `resources/physics-resources/quantum-gravity/index.html` | Quantum Gravity resources. |

Folder names use lowercase letters and hyphens. Visitors see readable titles such as “Physics Resources.”

## 1. Preview the website on your computer

1. Extract `physics-website.zip`.
2. Open the extracted folder.
3. Double-click the top-level `index.html` file to open it in your browser.
4. Click Resources, then Physics Resources, then General Relativity.

All internal links include `index.html` explicitly, so this local preview does not need a development server or an internet connection. The link to David Tong's course does need internet access.

## 2. Upload to GitHub

These instructions assume you are using the website repository from the earlier tutorial, typically `yourusername.github.io`.

1. Open that repository on GitHub.
2. Make sure you are on the branch used by GitHub Pages, usually `main`.
3. Click **Add file → Upload files**.
4. Open the extracted folder on your computer and drag its contents into the upload area: `index.html`, `style.css`, the entire `resources` folder, and optionally this `README.md`.
5. Check that the top-level `index.html` is directly in the repository, alongside `style.css`. Upload the contents, not another enclosing folder and not the ZIP archive itself.
6. Use a commit message such as `Organize theoretical physics resources` and commit directly to the publishing branch.

The new `index.html` and `style.css` replace the earlier tutorial versions if they already exist. The resources folder adds the new pages. If you have customized those two files, retain a copy first so you can bring your text across.

GitHub's upload documentation:
https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

## 3. Publish using GitHub Pages

In the repository, open **Settings → Pages** and use:

| Setting | Value |
| --- | --- |
| Source | Deploy from a branch |
| Branch | `main`, or the branch containing your uploaded files |
| Folder | `/(root)` |

Click **Save** if you changed the settings. If Pages was already configured this way, committing the files starts an update.

GitHub says updates may take up to 10 minutes. Use **Visit site** from Pages settings to find the correct public address. You can check the deployment in the **Actions** tab.

Official guidance:
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

The links in this website are relative. The same files therefore work at a personal site address such as `yourusername.github.io` or a project site address such as `yourusername.github.io/site/` without editing a username or base URL.

## 4. Edit your About page

Open the top-level `index.html` in GitHub and click the pencil icon. Edit the paragraphs inside the main content, then commit the change.

The starter identifies you only as Abel, a physics graduate student. You can add your preferred full name, academic background, and interests. The author name and navigation are repeated in each HTML page; if you change those shared elements, update all six HTML files. The stylesheet is already shared, so style changes need only one edit.

## 5. Add another resource

Open the topic page you want to change. For example:

`resources/physics-resources/general-relativity/index.html`

Find this list:

```html
<ul class="resource-list">
  <li>
    General relativity by David Tong |
    <a href="https://davidtong.org/teaching/general-relativity/">https://davidtong.org/teaching/general-relativity/</a>
  </li>
</ul>
```

Add a new `<li>...</li>` block immediately before the closing `</ul>`:

```html
<li>
  Resource title by Author Name |
  <a href="https://example.com/resource/">Course website</a>
</li>
```

Replace the example title, author, and address with the resource you actually want to add. The `href` value is the destination. The text between `<a>` and `</a>` is what visitors click; it can be the full URL or a shorter label such as “Lecture notes.”

Do not paste Markdown link syntax into an HTML list. Use the `<a href="...">...</a>` form above.

For the Quantum Field Theory and Quantum Gravity pages, replace this placeholder:

```html
<li class="empty-state">Resources will be added here.</li>
```

with your first real resource. Commit the file. You do not need to edit `style.css` when adding resources to an existing topic.

## 6. Keep the page white

The shared stylesheet contains:

```css
html,
body {
  margin: 0;
  background-color: #ffffff;
}
```

`#ffffff` is white. The header and footer also use white, and the site requests a light color scheme. The design has dark text, teal links, and thin gray dividers.

## 7. Create folders directly in GitHub if you prefer

GitHub can create nested folders when you type a path in **Add file → Create new file**. For example, entering:

`resources/physics-resources/general-relativity/index.html`

creates the required directories as part of saving the file. Paste the corresponding complete HTML file from this download and commit it. Repeat for the other files listed above. Uploading the extracted folder is usually faster for the first setup.

Official guidance:
https://docs.github.com/en/repositories/working-with-files/managing-files/creating-new-files

## Troubleshooting

| Problem | Check |
| --- | --- |
| Homepage gives a 404 | Pages is enabled; `index.html` is at the top level of the publishing folder; deployment has finished. |
| Homepage works but nested pages fail | The entire `resources` folder was uploaded with its subfolders. |
| Styling is missing | The root `style.css` exists and the relative stylesheet paths have not been changed. |
| A new resource is missing | You edited the correct topic's file, committed to the publishing branch, and waited for the deployment. |
| A link gives a 404 | Check the exact URL, filename, capitalization, and extension. |

## Design reference and first resource

The layout takes inspiration from the academic reading layout of Gabriele Di Ubaldo's website. This starter is an independent HTML/CSS implementation. Its own About text and CSS are original; it does not copy that site's biography, images, or resource descriptions.

- Design reference: https://philosophysics.github.io/site//
- First resource: https://davidtong.org/teaching/general-relativity/

No framework, JavaScript, package installation, or build step is needed for these files.
