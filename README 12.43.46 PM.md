# Alex Chudakov — Personal Portfolio

A fast, static, single-page website hosted free on GitHub Pages.

---

## 1. Get it online (first time, ~5 minutes)

1. Create a **public** GitHub repository named exactly:
   `alexanderchudakov.github.io`
2. Upload `index.html`, `404.html`, `CNAME`, and (optionally) `README.md`,
   plus an `/images/` folder for photos.
3. Go to the repo's **Settings → Pages**.
   - Source: **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)** → Save
4. Wait ~1 minute. The site is live at:
   `https://alexanderchudakov.github.io`

## 2. Connect the custom domain (later)

The `CNAME` file already contains `alexanderchudakov.com`.
After you buy the domain, add these DNS records at your registrar:

- Four `A` records pointing to:
  `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- One `CNAME` record for `www` → `alexanderchudakov.github.io`

Then in **Settings → Pages → Custom domain**, enter `alexanderchudakov.com`
and check **Enforce HTTPS** once it's available.

---

## 3. How to update the site

Everything lives in **`index.html`**. Open it and edit the text between the tags.
Each section is clearly marked with a comment like `<!-- ===== TENNIS ===== -->`.

### Change text
Find the words on the page inside `index.html` and type over them. Save. Done.

### Add a photo
1. Put the image file in an `/images/` folder (compress it first — aim under 400 KB).
2. Find the dashed placeholder block (search for `class="ph"`).
3. Replace the whole `<div class="ph">…</div>` with:
   ```html
   <img src="images/your-photo.jpg" alt="Short description of the photo"
        style="width:100%;border-radius:14px;display:block">
   ```

### Add a video (YouTube / Vimeo / Google Drive)
Replace a video placeholder (`class="ph ph-video"`) with:
```html
<div style="position:relative;aspect-ratio:16/9;border-radius:14px;overflow:hidden">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID"
    style="position:absolute;inset:0;width:100%;height:100%;border:0"
    allowfullscreen loading="lazy"></iframe>
</div>
```
(YouTube: the VIDEO_ID is the part after `watch?v=` in the URL.)

### Add the résumé
Save the résumé as `resume.pdf` in the repo root. The Download button already points to it.

### Update the UTR rating / date
In the **Tennis** section, find `UTR 7` and the `‹edit date›` tag and change them.

### Fill in email + GitHub
Search `index.html` for `you@example.com` and replace every instance with the real email.
Update the GitHub link in the footer if needed.

---

## 4. Still to add before going live
- [ ] Real main photo (Home)
- [ ] Real email address (replace `you@example.com`)
- [ ] `resume.pdf`
- [ ] `favicon.png` and `social-card.jpg` (1200×630) in the repo root
- [ ] Confirmed UTR date
- [ ] Photos / videos / certificates in each section
