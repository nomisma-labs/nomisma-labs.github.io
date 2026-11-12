# Nomisma Labs website

Static website for the Nomisma Labs development journal.

This repository is private during review. GitHub Pages has not been enabled.
The intended public address is <https://nomisma-labs.github.io/>.

`docs/` contains the complete generated website: a homepage, the 1 October and
2 October 2026 articles, shared CSS and the Nomisma coin logo. It contains no
unreviewed articles, editorial notes or source-repository history.

## Preview

```sh
python3 -m http.server 8000 --bind 127.0.0.1 --directory docs
```

Open <http://127.0.0.1:8000/>. The site uses root-relative URLs and should be served
from the root of a local HTTP server.

## Regenerate

Content, publication approval and templates are maintained in the separate private
blog repository. From that checkout, follow `website/README.md`, then run:

```sh
website/.venv/bin/python website/build.py --output ../nomisma-labs.github.io/docs
```

Review the generated diff, commit and push. Do not edit generated files directly.
The converter selects approved articles explicitly and rebuilds the homepage and
article navigation from that selection.

## Publish later

When review is complete:

1. Make this website repository public. The source blog can remain private.
2. Open Settings → Pages.
3. Select Deploy from a branch, `master`, and `/docs`.
4. Wait for the Pages deployment and check the live website.

The `.nojekyll` file disables Jekyll processing of the prebuilt output. No separate
build workflow, runtime service or secret is needed. Making the repository public
does not enable Pages automatically.

GitHub Pages hosting can be public even when the repository is private. Keep Pages
disabled while using local previews for review. See the [GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).
