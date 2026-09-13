# Platka Image-to-Text

![Platka Image-to-Text logo](./logo.png)

Platka Image-to-Text is a fast, privacy-focused OCR web application for converting text inside images into editable text. It runs entirely in the browser using [Tesseract.js](https://github.com/naptha/tesseract.js), so no backend, API key, database, or build step is required.

## Live website

**Production:** [https://platka-image-text.pages.dev](https://platka-image-text.pages.dev)

**GitHub:** [https://github.com/candrabasic/image-to-text](https://github.com/candrabasic/image-to-text)

## Features

- Upload images by clicking, dragging and dropping, or pressing `Ctrl + V` with an image in the clipboard.
- Supports `JPG`, `PNG`, and `WEBP` files.
- Maximum upload size: `10 MB`.
- Image preview before OCR processing.
- Browser-based OCR powered by Tesseract.js.
- English and Indonesian OCR using the `ind+eng` trained language data.
- Live OCR progress indicator.
- Editable OCR output in a textarea.
- Copy extracted text using the Clipboard API, with a fallback for older browsers.
- Paste text from the clipboard with the **Paste** button.
- Paste an image directly from the clipboard with `Ctrl + V`.
- Responsive layout for desktop, tablet, and mobile devices.
- Animated modern interface with accessible keyboard interactions.
- Privacy Policy and Terms & Conditions dialogs.
- SEO metadata, Open Graph cards, Twitter cards, JSON-LD structured data, `robots.txt`, and `sitemap.xml`.
- No user account, server upload, or image storage.

## How to use

1. Open the [live website](https://platka-image-text.pages.dev).
2. Add an image using one of these methods:
   - Drag and drop it into the upload area.
   - Click **browse files** and select an image.
   - Copy an image from another application and press `Ctrl + V`.
3. Review the image preview.
4. Click **Extract text**.
5. Wait for OCR to finish.
6. Edit the result if needed.
7. Click **Copy text**, or use **Paste** to insert text from your clipboard.

### Clipboard image notes

Image pasting uses the browser `paste` event and reads image data from the clipboard. It works best when:

- The website is opened over HTTPS.
- The browser has permission to access the clipboard.
- The copied content is an actual image, such as a screenshot or copied image file.

If clipboard access is unavailable, use the file picker or drag-and-drop upload instead.

## Project structure

```text
image_to_text/
├── index.html       # Page markup, SEO metadata, structured data, legal dialogs
├── style.css        # Responsive design, animations, layout, and theme
├── script.js        # Upload, preview, OCR, progress, clipboard, and interactions
├── logo.png         # Platka brand logo and favicon source
├── robots.txt       # Search engine crawling instructions
├── sitemap.xml      # Search engine sitemap
├── .gitignore       # Ignores local Wrangler files and node_modules
└── README.md        # Project documentation
```

## Technology

- HTML5
- CSS3
- Vanilla JavaScript
- [Tesseract.js v5 via jsDelivr CDN](https://cdn.jsdelivr.net/npm/tesseract.js@5/dist/tesseract.min.js)
- Cloudflare Pages
- Google Fonts: DM Sans and Space Grotesk

There is no Node.js build process. The project is a static website and can be opened or deployed directly.

## Run locally

For a quick local preview, open `index.html` in a browser. For the most reliable OCR and clipboard behavior, serve the folder over a local HTTP server.

### Python local server

```bash
python -m http.server 8080
```

Then open [http://localhost:8080](http://localhost:8080).

### Wrangler local preview

If Wrangler is available:

```bash
npx wrangler pages dev .
```

## Deploy to Cloudflare Pages

### Wrangler CLI

1. Install [Node.js](https://nodejs.org/).
2. Open a terminal in the project directory.
3. Log in to Cloudflare:

   ```bash
   npx wrangler login
   ```

4. Create the Pages project once:

   ```bash
   npx wrangler pages project create platka-image-text --production-branch main --force
   ```

5. Deploy the static files:

   ```bash
   npx wrangler pages deploy . --project-name platka-image-text
   ```

The production URL is:

```text
https://platka-image-text.pages.dev
```

### Cloudflare Dashboard drag and drop

1. Open the [Cloudflare Dashboard](https://dash.cloudflare.com/).
2. Go to **Workers & Pages**.
3. Select **Create application** → **Get started** → **Drag and drop your files**.
4. Set the project name to:

   ```text
   platka-image-text
   ```

5. Drag the project folder into the upload area.
6. Select **Deploy site**.

## SEO checklist

The project includes the main technical SEO files and tags:

- Descriptive title and meta description.
- Search keywords and author metadata.
- Canonical production URL.
- `index, follow` robots directive.
- Open Graph title, description, URL, and logo image.
- Twitter Card metadata.
- JSON-LD `WebApplication` schema with publisher information.
- `robots.txt` pointing to the sitemap.
- `sitemap.xml` for the production URL.
- Semantic sections, heading hierarchy, descriptive links, and image alt text.

After deployment, submit the sitemap to Google Search Console:

```text
https://platka-image-text.pages.dev/sitemap.xml
```

## Privacy

OCR runs locally in the user's browser. The selected image is not uploaded to a Platka server or stored by this project. Tesseract.js and web fonts are loaded from external CDNs, so normal browser network request information may be visible to those CDN providers.

Read the in-app [Privacy Policy](https://platka-image-text.pages.dev/#privacy) and [Terms & Conditions](https://platka-image-text.pages.dev/#terms) for the current service notices.

## Contact

- Email: [platkasoftwaredigital@gmail.com](mailto:platkasoftwaredigital@gmail.com)
- Phone: `081111102880`
- Official website: [platkadigital.com](https://platkadigital.com)
- Product website: [platka.io](https://platka.io)

## License

This repository is maintained for Platka Digital. Contact Platka Digital before redistributing or reusing the brand assets, logo, or product content.
