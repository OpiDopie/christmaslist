# Jack's Christmas List 2026

A static Christmas presentation and local editor. No build, package installation, backend, account service, or paid hosting required.

## Put it on GitHub Pages

1. Extract this ZIP.
2. Create a GitHub repository (a public repository works with GitHub Free).
3. Upload the **contents** of the christmas-list folder to the repository root: index.html, editor.html, app.js, style.css, gifts.json, and .nojekyll. Do not upload the ZIP itself.
4. Open repository Settings → Pages. Under Build and deployment choose **Deploy from a branch**, then **main** and **/(root)**. Save.
5. Wait for deployment. Open the website URL shown in Pages settings. It is usually https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/.

## Add and edit gifts

Open **Edit list**. Enter a product name, price in USD, priority from 1 to 100, optional notes, product link, and image. Upload a JPG, PNG, or WebP photo, paste a direct image URL, or enter a relative path such as assets/lens.jpg. Photos uploaded in the editor are resized and embedded in the JSON export. Click **Add gift** or **Save gift**.

Drafts save in this browser only. Use **Preview draft** to see the presentation. When ready, click **Export gifts.json**, upload that file over the repository's existing gifts.json, and commit. GitHub Pages will deploy the change. Refresh the published page after deployment. Export does not include an unsaved gift form; save that gift first.

Only your GitHub repository permissions control publication. The editor is not password protected: anyone may open it, but changes affect only their own browser. No visitor can change the published list through this editor. Do not put tokens, passwords, or private data in this public repository. Private authenticated administration and cross-device saving require a backend, which this project deliberately does not use.

Browser drafts can be lost if browsing data is cleared. Export backups. If local storage fills up, export immediately. Photo files in assets/ can keep gifts.json smaller. Uploaded editor photos do not require separately uploading image files.

## Edit JSON directly

Edit gifts.json on GitHub. Example (replace with your real item):

```json
{
  "title": "Jack's Christmas List",
  "year": 2026,
  "gifts": [
    {
      "name": "Your gift name",
      "price": 49.99,
      "rank": 90,
      "image": "assets/your-photo.jpg",
      "link": "https://example.com/product",
      "notes": "Black, size large."
    }
  ]
}
```

Price is a number without a dollar sign. Rank is an integer from 1 to 100. Higher priorities appear first; equal priorities retain file order. All optional text fields can be empty strings. The title is editable; the decorative J✦26 mark and intro date can be changed in the HTML if you reuse the site for someone else or another year. No real gifts or invented prices are preloaded.

## Presentation

Each gift occupies a two-screen scrolling section with a full-screen sticky stage. The image and name arrive first; continued scrolling reveals price, notes, and the store link. The final summary shows every gift, its priority, notes, price, and store link. The total is the sum of one of each gift; it excludes tax and shipping. The priority bar fades from red (1) through yellow to green (100), with a marker showing each gift's score.

Mobile layout stacks the photo above the details. Reduced-motion preferences disable snow and the staged reveals, keeping all information visible. Print from the browser for a condensed list. Broken or missing images show a gift icon.

## Local preview

Do not double-click index.html: browsers often block local JSON fetching. Run `python3 -m http.server 8000` in this folder, then open http://localhost:8000. No server is needed beyond GitHub Pages when deployed.

GitHub reference: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
