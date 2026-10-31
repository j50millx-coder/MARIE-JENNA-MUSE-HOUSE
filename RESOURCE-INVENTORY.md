# Muse House website — resource inventory

## Folder layout

```
muse-house-github-ready/
├── index.html
└── assets/
    └── images/
        ├── banner-primary.png
        ├── banner-alternate.png
        ├── profile.png
        ├── checkout-visual.png
        ├── payment-methods.png
        └── posts/
            └── 1.jpg … 11.jpg
```

All files that were supplied locally have been gathered under `assets/images` and renamed for their on-page role. `index.html` points to these new local paths.

## Current edit points

- The banner is shown at the source image's full 3.29:1 aspect ratio and uses contained, naturally saturated rendering so no portion is cropped.
- The profile status dot uses a repeating green glow animation.
- The `posts` array in `index.html` has one `caption` value per current post. Replace the eleven clearly labelled placeholder values with the final ordered captions; each caption is rendered immediately above its like, comment, save, and share controls.

## Current post images

The eleven supplied post images are stored in `assets/images/posts/` and are rendered in ascending chronological order: `1.jpg` through `11.jpg`.

## Runtime services retained

All static resources—the page, every referenced image, and the page styling—are stored in this folder. Google Fonts and the unused Unsplash image reference have been removed, so fonts fall back to browser-native typefaces.

Two live services remain intentionally external because they cannot be packaged as static files:

- Paystack’s checkout script (`https://js.paystack.co/v1/inline.js`)
- A live USD/NGN exchange-rate request to `https://api.frankfurter.dev/v2/rate/usd/ngn`

These require an internet connection. The page includes a Paystack public key and opens a real checkout flow; test it carefully and configure server-side payment verification before using it with customers.
