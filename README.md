# Abel Shiferaw's webpage

This version is a single-page website inspired by the plain academic format of Daniel Harlow's webpage: https://www.mit.edu/~harlow/

Everything is in `index.html`, including the small CSS style block. The page has a white background, black serif text, conventional blue links, and nested resource lists.

The page follows this order:

1. Abel Shiferaw's webpage.
2. A temporary place for your photograph.
3. Your exact welcome paragraph.
4. Resources: General relativity; Quantum Field Theory; Quantum Gravity, and Black Holes.

All seven resource URLs are retained exactly as supplied. Only the photo is still to be added.

## Preview

1. Extract `physics-website.zip`.
2. Open its `index.html` file in a browser.

You can preview the page locally. Following the resource links requires internet access.

## Update your GitHub website

1. Open the GitHub repository used for your website.
2. Stay on the branch used by GitHub Pages, usually `main`.
3. Choose **Add file → Upload files**.
4. Upload the extracted `index.html` directly to the repository's top level, replacing the previous homepage.
5. Commit the change with a message such as `Switch to a single-page physics resource website`.
6. Keep **Settings → Pages → Deploy from a branch → main → /(root)**, using your actual publishing branch if it has another name.
7. Wait for deployment and refresh the published page. GitHub says changes can take up to 10 minutes to publish.

Upload the HTML file itself, not the ZIP archive or an enclosing folder. You may also replace your repository's README with this one, but the README is not needed to render the website.

The new homepage contains all your resources. It does not load the old `style.css` or link to the previous `resources` folder. GitHub does not automatically remove old repository files when you upload the new homepage; the previous topic pages remain accessible at their old addresses until you delete them. Once you have switched, you can delete that obsolete stylesheet and the old topic pages from the repository if you want the published site to contain only this new page. Commit those deletions as well.

Official GitHub instructions:
- https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Add your picture

You can send your picture in the conversation to have it fitted into the page, or add it yourself:

1. Upload a JPEG named `profile.jpg` to the same repository folder as `index.html`. If the picture is a PNG, keep the `.png` extension and use that exact filename in the next step. Changing a filename extension does not convert the image format.
2. Edit `index.html` and find this temporary placeholder:

```html
<div class="photo-placeholder" role="img" aria-label="Space reserved for a photo of Abel Shiferaw">Photo to be added</div>
```

3. Replace that entire div with:

```html
<img class="profile-photo" src="profile.jpg" alt="Abel Shiferaw">
```

4. Commit the change.

The picture appears directly under your title. Its displayed width is limited to 600 pixels, and it shrinks to fit narrow screens. Its original aspect ratio is preserved. Change `width: 600px` in `.profile-photo` if you want a smaller picture.

The commented example in the HTML is for guidance; an HTML comment between `<!--` and `-->` is not displayed.

## Add another resource

Edit `index.html` in GitHub. Find the nested `<ul>` under the desired subject, and add a new entry before that nested list's closing `</ul>`:

```html
<li>
  Author Name |
  <a href="https://example.com/resource/">https://example.com/resource/</a>
</li>
```

Replace the example author and URL with your actual resource. The address inside `href` is the link destination; the text between `<a>` and `</a>` is what visitors see. Commit the change.

## Change the appearance

The `<style>` block near the top of `index.html` controls the whole page:

- `background-color: #ffffff` keeps the page white.
- `color: #000000` makes the body text black.
- `font-family: "Times New Roman", Times, serif` selects a traditional serif font.
- `overflow-wrap: anywhere` allows long resource URLs to wrap on smaller screens.

This version does not require a separate stylesheet, a framework, JavaScript, or a build step.
