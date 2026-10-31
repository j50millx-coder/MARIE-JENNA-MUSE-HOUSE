# Muse House — GitHub and Vercel upload package

This is a static website package. Upload the **contents of this folder** to the root of a GitHub repository; keep the folder structure unchanged.

```
.
├── index.html
├── README.md
├── RESOURCE-INVENTORY.md
└── assets/
    └── images/
        ├── banner-primary.png
        ├── banner-alternate.png
        ├── profile.png
        ├── checkout-visual.png
        ├── payment-methods.png
        └── posts/
            ├── 1.jpg
            ├── 2.jpg
            └── … through 11.jpg
```

## Deploy with Vercel

1. Create a new GitHub repository and upload the contents of this folder to its root.
2. In Vercel, select **Add New → Project**, then import that repository.
3. Vercel will recognize this as a static HTML site. Do not set a build command or output directory.
4. Deploy.

No framework, package manager, or build step is required. The page uses relative resource paths such as `assets/images/posts/1.jpg`, so the images will load correctly after deployment as long as this structure is preserved exactly.

## Live checkout services

The Paystack checkout script and the live USD/NGN exchange-rate lookup deliberately remain internet services. They are not image or static-file dependencies and must stay reachable for live checkout to work. Before accepting production payments, use secure server-side verification of Paystack payment references.
