# Chang Sun

Personal website and writing archive built with [Astro](https://astro.build/)
and customized from
[AstroPaper](https://github.com/satnaing/astro-paper).

This repo currently tracks **AstroPaper v5.5.1** and keeps the original
template repo configured as a Git remote named `upstream` to make future
template updates easier.

## Stack

- Astro 5
- Tailwind CSS 4
- TypeScript
- Pagefind search
- Dynamic OG image generation

## Project layout

```text
.
├── public/
├── src/
│   ├── assets/
│   ├── components/
│   ├── data/
│   │   └── blog/
│   ├── layouts/
│   ├── pages/
│   ├── styles/
│   ├── utils/
│   ├── config.ts
│   ├── constants.ts
│   └── content.config.ts
├── astro.config.ts
└── package.json
```

## Content

- Blog posts live in `src/data/blog/`
- Site metadata lives in `src/config.ts`
- Social links live in `src/constants.ts`
- Homepage content lives in `src/pages/index.astro`
- About page content lives in `src/pages/about.md`

## Local development

```bash
pnpm install
pnpm run dev
```

Useful commands:

```bash
pnpm run build
pnpm run preview
pnpm run lint
pnpm run format
pnpm exec astro check
```

## Template updates

Check the configured remotes:

```bash
git remote -v
```

Fetch the latest AstroPaper changes:

```bash
git fetch upstream --prune --tags
```

Compare this repo with the upstream template:

```bash
git log --oneline --left-right HEAD...upstream/main
git diff --stat HEAD..upstream/main
git diff HEAD..upstream/main -- astro.config.ts package.json src public
```

Recommended workflow for future upgrades:

```bash
git checkout -b codex/template-update
git fetch upstream --prune --tags
git diff HEAD..upstream/main -- astro.config.ts package.json src public
```

Then port upstream changes selectively, run checks, and merge the branch when
ready.
