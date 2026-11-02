# PS4 14.00 GoldHEN

Static GitHub Pages package for the 14.00 GoldHEN launcher tested on a retail
PS4. Opening the site root starts the browser entry and GoldHEN chain.

## Publish

1. Create a GitHub repository named `ps4-14.00-jb`.
2. Upload the **contents of this folder** to the repository root, so
   `index.html`, `.nojekyll`, and `raw13/` are at the top level.
3. In **Settings → Pages**, choose **Deploy from a branch**, `main`, and
   `/(root)`. The site URL will be
   `https://YOUR-USERNAME.github.io/ps4-14.00-jb/`.

GitHub's [Pages publishing guide](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
shows the current branch and root settings.

The page needs no server code. The launch URL disables the `/t` marker POSTs
used by the local research server. All asset references are relative, so the
site works under the repository path.

## Use

On a cold-booted PS4 running firmware 14.00, open the Pages URL in the PS4
browser. The page starts automatically and displays its step log. If the
browser entry exhausts its attempts before reaching the kernel stage,
refresh to retry. After a run reaches the D-stage `EV_ADD` or applies the
kernel patch, cold boot before another run.

The pinned local run returned `L-HEN-DIRECT-RETURN rc=0` and showed
`hen 14.00` and `★ Goldhen V2.4b18.12 ★ by Sistro` in System Information.
This package has been checked as a static site; the Pages-hosted copy still
needs a console run after publication.

## Provenance

The launcher is based on the local Silver source pinned to commit
`696c54780d8af11924c7d36bbd3aa6837b8d55f8` of
[silverps4hen](https://github.com/aminegold0/silverps4hen), with the 14.00
held-stage continuation and donated GoldHEN image. `raw13/LICENSE` preserves
the upstream notice for code authored by raw13g. Bundled binaries and
third-party components retain their respective rights; the MIT notice does
not relicense them.

The `raw13/hen.bin` image is the same locally tested adaptation. It changes
only the failure returns for its optional `/data` diagnostic file logger.
The kernel calls and their result checks are unchanged. The kernel patch is
Silver's 14.00 `raw13/patches/1400.bin`.

| File | SHA-256 |
| --- | --- |
| `raw13/hen.bin` | `756077919fd59abd0eb3ae7b96b6295349b2a0a1b6a7d5c99b3c6898c4abe753` |
| `raw13/patches/1400.bin` | `165d2ad966b3829d1fbcb53d5e7ecbc20563de4a6a49ee70d8126d0256a49c02` |
