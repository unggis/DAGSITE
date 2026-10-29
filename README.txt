DONNAGESSELL.COM — STATIC SITE
================================

This folder is the complete website. Every page from the old WordPress site is
here, with the same look, minus the database and plugins.

STEP 1 — ADD THE ART PHOTOS
---------------------------
Copy these 14 files from the WordPress backup (wp-content/uploads/...)
into this folder's "images" folder. Don't rename them.

  uploads/2026/03/05-Back-scaled.png
  uploads/2026/03/05-Front-scaled.png
  uploads/2026/03/10-Backv1-scaled.jpg
  uploads/2026/03/10-Frontv1-scaled.jpg
  uploads/2026/02/14-Back-scaled-1.jpg
  uploads/2026/02/14-Front-scaled-1.png
  uploads/2026/02/20-Back-scaled.jpg
  uploads/2026/02/20-Front-scaled_adjusted.jpg
  uploads/2026/03/26-Frontcropped.png
  uploads/2026/03/42-Back.png
  uploads/2026/03/42-Front-scaled.png
  uploads/2026/03/63-Front.png
  uploads/2026/02/64-Back-scaled.png
  uploads/2026/02/64-Front.png

That's all the site uses right now. (The other ~60 photographed pieces were
never published on the old site. They can be added later.)

STEP 2 — PUT IT ON GITHUB
-------------------------
1. github.com -> New repository -> name it "donnagessell-site" -> Private is fine -> Create.
2. On the new repo page: "uploading an existing file" -> drag in EVERYTHING inside
   this folder (not the folder itself) -> Commit changes.
   (index.html, _redirects and 404.html must be at the top level of the repo.)

STEP 3 — PUBLISH ON CLOUDFLARE PAGES
------------------------------------
1. Cloudflare dashboard -> Workers & Pages -> Create -> Pages -> Connect to Git.
2. Pick the donnagessell-site repo.
3. Build settings: Framework preset = None, Build command = (leave empty),
   Build output directory = /   -> Save and Deploy.
4. You get a test address like donnagessell-site.pages.dev. Check it.

STEP 4 — SWITCH THE DOMAIN OVER (only after the test address looks right)
------------------------------------------------------------------------
1. In the Pages project -> Custom domains -> Set up a custom domain ->
   donnagessell.com, then add www.donnagessell.com too.
2. Cloudflare offers to replace the old A / AAAA records pointing at Hostinger.
   Accept. Leave the MX and TXT records alone (that's Donna's email via ImprovMX).
3. Delete the old "ftp" A record and the hostingermail / autoconfig /
   autodiscover records. They only served Hostinger.

Do Step 4 before the Hostinger month ends (11/29).

UPDATING THE SITE LATER
-----------------------
Edit a file on GitHub (pencil icon) or upload a replacement -> Commit.
Cloudflare republishes automatically in about a minute.

Old WordPress links (donnagessell.com/index.php/...) automatically redirect to
the new addresses via the _redirects file.
