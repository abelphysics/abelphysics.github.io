# Abel Shiferaw's webpage

This version is a single-page website inspired by the plain academic format of Daniel Harlow's webpage: https://www.mit.edu/~harlow/

The page and its small CSS style block are in `index.html`. Your photograph is included as `Abel.jpeg` alongside it. The page has a white background, black serif text, conventional blue links, and nested resource lists.

The page follows this order:

1. Abel Shiferaw's webpage.
2. Your photograph.
3. Your exact welcome paragraph.
4. Resources: General relativity; Quantum Field Theory; Quantum Gravity, and Black Holes.

All seven resource URLs are retained exactly as supplied. Your photograph is included and displayed directly beneath the title.

## Preview

1. Extract `physics-website.zip`.
2. Open its `index.html` file in a browser.

You can preview the page locally. Following the resource links requires internet access.

## Update your GitHub website

1. Open the GitHub repository used for your website.
2. Stay on the branch used by GitHub Pages, usually `main`.
3. Choose **Add file → Upload files**.
4. Upload both extracted files, `index.html` and `Abel.jpeg`, directly to the repository's top level, replacing the previous homepage.
5. Commit the change with a message such as `Add my photograph to the homepage`.
6. Keep **Settings → Pages → Deploy from a branch → main → /(root)**, using your actual publishing branch if it has another name.
7. Wait for deployment and refresh the published page. GitHub says changes can take up to 10 minutes to publish.

Upload the HTML file and photograph themselves, not the ZIP archive or an enclosing folder. Keep `index.html` and `Abel.jpeg` together in the same folder. You may also replace your repository's README with this one, but the README is not needed to render the website.

The new homepage contains all your resources. It does not load the old `style.css` or link to the previous `resources` folder. GitHub does not automatically remove old repository files when you upload the new homepage; the previous topic pages remain accessible at their old addresses until you delete them. Once you have switched, you can delete that obsolete stylesheet and the old topic pages from the repository if you want the published site to contain only this new page. Commit those deletions as well.

Official GitHub instructions:
- https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Your picture

Your original photograph is included as `Abel.jpeg`. The page displays it with:

```html
<img class="profile-photo" src="Abel.jpeg" alt="Abel Shiferaw" width="1536" height="2048">
```

The filename is case-sensitive, so keep the capital A in `Abel.jpeg`. The image is displayed 360 pixels wide on larger screens and shrinks to fit narrower screens. Its proportions are preserved. The original photograph is included without cropping or other image changes.

To change its displayed size, edit `width: 360px` inside the `.profile-photo` CSS rule. Leave `height: auto` to preserve its proportions. The HTML width and height attributes describe the image's original dimensions so the browser can reserve the correct proportions before it loads.

If you replace the photograph later, upload the new image and update the `src`, `width`, and `height` attributes to match it.

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
