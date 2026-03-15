# Handy Harvest Website

Astro website for Handy Harvest, designed for deployment on Cloudflare Pages.

## Local development

```bash
npm install
npm run dev
```

## Environment variables

Copy `.env.example` to `.env` for local use.

- `PUBLIC_SITE_URL`
  - Your deployed site URL, for example `https://handyharvest.pages.dev`
- `PUBLIC_FORMSUBMIT_TARGET`
  - The form receiver used by FormSubmit. This can be a Gmail address such as `yourname@gmail.com`
  - After activation, FormSubmit also lets you swap the public email for its generated target token if you do not want the email shown in the form action

## Cloudflare Pages

Use these build settings:

- Framework preset: `Astro`
- Build command: `npm run build`
- Build output directory: `dist`
- Production branch: `main`

Set these environment variables in Cloudflare Pages:

- `PUBLIC_SITE_URL`
- `PUBLIC_FORMSUBMIT_TARGET`

## Form setup

The contact form posts to FormSubmit and forwards submissions to the configured receiver.

1. Set `PUBLIC_FORMSUBMIT_TARGET` to your Gmail address in Cloudflare Pages.
2. Deploy the site.
3. Submit the form once.
4. Confirm the activation email from FormSubmit.
5. Future submissions will then be delivered to that inbox.
