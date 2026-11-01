# Muse House — Vercel deployment package

This folder is the complete deployment root. Upload the **contents of this folder**, not the folder above it, to the root of your GitHub repository.

## Required deployment structure

```text
repository-root/
├── index.html
├── README.md
├── ASSET-MANIFEST.md
├── vercel.json
└── assets/
    ├── banner/
    │   └── marie-banner-primary.png
    ├── profile/
    │   └── marie-profile.png
    ├── checkout/
    │   ├── marie-checkout-visual.png
    │   └── payment-methods.png
    ├── posts-01-to-06/
    │   ├── marie-post-01.jpg
    │   └── … through marie-post-06.jpg
    └── posts-07-to-11/
        ├── marie-post-07.jpg
        └── … through marie-post-11.jpg
```

Every image reference in `index.html` uses the same lowercase path and filename as the file in the matching `assets/` subfolder. This matters because Vercel deploys on a case-sensitive Linux filesystem.

## Deploy to Vercel

1. Create a new empty GitHub repository.
2. Upload all files and folders inside this package to the repository root. `index.html` must be at the root, at the same level as `assets`.
3. On Vercel, choose **Add New → Project**, import the repository, and deploy.
4. Leave the framework preset as **Other**. No build command and no output directory are needed.

The `vercel.json` file tells Vercel to serve this as a static website and applies long cache lifetimes to all files in `assets/`.

## External live services

The Paystack checkout script and live USD/NGN exchange-rate lookup intentionally remain online services. Every image and other static website resource is included locally in this package.
