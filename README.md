# FloodBlock Landing (Static)

A zero-build static landing page for FloodBlock, deployable on GitHub Pages.

## Quick Start
1. Create a repo, e.g. `floodblock-site`.
2. Upload the files in this folder to the repo root.
3. Enable **Settings → Pages → Deploy from branch** and pick your default branch `/ (root)`.
4. Visit `https://<username>.github.io/<repo>/`.

## Wire Google Forms (Custom POST)
1. Create a Google Form with fields: Name, Email, Phone, Property Type, Message.
2. Open the live form, right-click **View page source** and search for `formResponse`.
3. Copy the form action URL (looks like `https://docs.google.com/forms/d/e/FORM_ID/formResponse`).
4. For each field, find its `entry.xxxxxx` id. Update the `GF_CONFIG` object in `index.html`:
   ```js
   const GF_CONFIG = {
     formAction: "https://docs.google.com/forms/d/e/FORM_ID/formResponse",
     fields: {
       name: "entry.111111",
       email: "entry.222222",
       phone: "entry.333333",
       property: "entry.444444",
       message: "entry.555555"
     }
   };
   ```
5. Commit and push. Submissions will appear in the Google Form responses (and linked Sheet).

### Alternative: Embed the Google Form
- Replace the `<form id="quoteForm">...</form>` block with the iframe snippet Google provides.

## Customize
- Brand colors are controlled by the `.gradient-bg` CSS rule in `index.html`.
- Replace images in `/assets` (logo/product photos). Update paths if filenames change.
- Edit copy directly in the HTML sections.

## License
© FloodBlock. All rights reserved.
