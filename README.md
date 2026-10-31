<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/grafanaKibana/web-portfolio-v1/HEAD/docs/assets/product-captures/hero-dark.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/grafanaKibana/web-portfolio-v1/HEAD/docs/assets/product-captures/hero.png">
  <img src="https://raw.githubusercontent.com/grafanaKibana/web-portfolio-v1/HEAD/docs/assets/product-captures/hero.png" alt="Product overview">
</picture>

<p align="center">
Personal portfolio built with Angular, with an animated WebGL background, a Markdown blog, and data-driven resume sections.
</p>

<p align="center">
<a href="https://old.reshetnik.dev"><picture><source media="(prefers-color-scheme: dark)" srcset="https://shieldcn.dev/badge/Legacy_site.svg?variant=default&amp;size=sm&amp;font=geist&amp;mode=dark&amp;logo=ri%3ALuArrowUpRight&amp;color=84cc16&amp;logoColor=0e100f&amp;valueColor=0e100f&amp;labelTextColor=0e100f&amp;gradient=84cc16%2C95d133%2C110"><img alt="Legacy site" src="https://shieldcn.dev/badge/Legacy_site.svg?variant=default&amp;size=sm&amp;font=geist&amp;mode=light&amp;logo=ri%3ALuArrowUpRight&amp;color=437100&amp;logoColor=ffffff&amp;valueColor=ffffff&amp;labelTextColor=ffffff&amp;gradient=437100%2C4c7a10%2C110"></picture></a>
<a href="https://github.com/grafanaKibana/web-portfolio-v1/issues"><picture><source media="(prefers-color-scheme: dark)" srcset="https://shieldcn.dev/badge/Report_an_issue.svg?variant=outline&amp;size=sm&amp;font=geist&amp;mode=dark&amp;logo=ri%3ALuBug&amp;gradient=18181b%2C18181b%2C90&amp;logoColor=fafafa&amp;labelTextColor=fafafa"><img alt="Report an issue" src="https://shieldcn.dev/badge/Report_an_issue.svg?variant=outline&amp;size=sm&amp;font=geist&amp;mode=light&amp;logo=ri%3ALuBug&amp;gradient=fafafa%2Cfafafa%2C90&amp;logoColor=18181b&amp;labelTextColor=18181b" style="display:inline-block;margin:0;vertical-align:middle"></picture></a>
<a href="https://github.com/grafanaKibana/web-portfolio-v1/pulls"><picture><source media="(prefers-color-scheme: dark)" srcset="https://shieldcn.dev/badge/Contributing.svg?variant=outline&amp;size=sm&amp;font=geist&amp;mode=dark&amp;logo=ri%3ALuGitPullRequest&amp;gradient=18181b%2C18181b%2C90&amp;logoColor=fafafa&amp;labelTextColor=fafafa"><img alt="Contributing" src="https://shieldcn.dev/badge/Contributing.svg?variant=outline&amp;size=sm&amp;font=geist&amp;mode=light&amp;logo=ri%3ALuGitPullRequest&amp;gradient=fafafa%2Cfafafa%2C90&amp;logoColor=18181b&amp;labelTextColor=18181b" style="display:inline-block;margin:0;vertical-align:middle"></picture></a>
</p>

## Get started

Browse Home for experience, education, skills, and contact links. The Blog lists technical articles, each with its own `/blog/:slug` URL and highlighted code blocks.

The CV download retrieves a PDF from the LaTeX CV repository’s GitHub Actions artifacts. Download availability depends on that external artifact.

## Local setup

Use Node.js 22 and npm. The project includes its own Angular CLI.

```bash
npm ci
npm start
```

Open [localhost:4200](http://localhost:4200). Run `npm run build` for a production build or `npm test` for Jest. The test script includes Node’s experimental VM modules flag.

## How it works

Angular standalone components render the resume sections from one cached JSON request. The blog reads a Markdown registry, loads the listed posts, parses their metadata, and sorts them by publication date.

The WebGL background supplies colors to CSS custom properties used by the glass reflections. Palettes, animation settings, and reflection tuning share [webgl.config.ts](src/app/config/webgl.config.ts). A CSS gradient is used when WebGL is unavailable.

The opening introduction supports Space or Escape to skip, remembers completion for the browser session, and bypasses the sequence for reduced-motion preferences.

## Update content

Change [home-data.json](src/assets/data/home-data.json) for profile details, resume sections, and header flags. Add Markdown under [blog posts](src/assets/data/blog/posts/) and list its path in [index.md](src/assets/data/blog/index.md). Use an existing post as the metadata example.

## Guides

- [Responsive styling guide](src/assets/styles/README.md) — Breakpoints, layout mixins, and responsive utilities.
