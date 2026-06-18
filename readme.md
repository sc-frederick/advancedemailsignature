# Advanced Engineering Email Signature

Hosted image assets for the Advanced Engineering Consultants email signature. The PNGs in `images/` are referenced directly from signature HTML using their raw GitHub URLs, so signatures load the icons from this repo with no external image host.

## Repository structure

```
images/
  AdvancedLogo.png    Company logo
  facebook.png        Facebook icon
  instagram.png       Instagram icon
  linkedin.png        LinkedIn icon
  yelp.png            Yelp icon
LICENSE
readme.md
```

## Using the images

Reference each asset by its raw URL. Use the `raw.githubusercontent.com` host, which serves the actual image bytes. Do not use the `github.com/.../blob/...` URL, which returns an HTML page rather than an image and will render as a broken image in email clients.

Base path:

```
https://raw.githubusercontent.com/sc-frederick/advancedemailsignature/main/images/<filename>
```

| Asset | Raw URL | Display size |
| --- | --- | --- |
| Logo | `.../images/AdvancedLogo.png` | 127x140 |
| Facebook | `.../images/facebook.png` | 22x22 |
| Instagram | `.../images/instagram.png` | 24x24 |
| LinkedIn | `.../images/linkedin.png` | 22x22 |
| Yelp | `.../images/yelp.png` | 22x22 |

Example:

```html
<img src="https://raw.githubusercontent.com/sc-frederick/advancedemailsignature/main/images/AdvancedLogo.png"
     width="127" height="140" alt="Advanced Engineering Logo">
```

## Image format and optimization

Format is PNG by design. Email clients, in particular Outlook desktop (Word rendering engine), do not reliably support WebP, AVIF, or SVG. PNG is universally supported and preserves the transparency these assets require.

The assets are optimized for email weight:

- Stored at 2x their display size for retina sharpness (logo 254x280, icons 48x48).
- Quantized to PNG-8 (indexed palette) with alpha preserved.
- Losslessly compressed with oxipng.

All five graphics are solid black artwork on a transparent background, so palette and grayscale reduction are color-faithful. Combined, the asset set is roughly 6 KB.

| File | Size | Dimensions |
| --- | --- | --- |
| AdvancedLogo.png | ~5.0 KB | 254x280 |
| facebook.png | ~0.2 KB | 48x48 |
| instagram.png | ~0.4 KB | 48x48 |
| linkedin.png | ~0.3 KB | 48x48 |
| yelp.png | ~0.3 KB | 48x48 |

## Notes

- When replacing an asset, keep the existing filename so signature HTML needs no changes.
- Raw GitHub URLs are pinned to the `main` branch. Changes pushed to `main` propagate to live signatures, subject to GitHub's raw-content caching (typically a few minutes).

## License

See [LICENSE](LICENSE).
