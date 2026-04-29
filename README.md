# Akshay Chame HyperFrames Portfolio

A cinematic portfolio built from Akshay Chame's resume using [HyperFrames](https://github.com/heygen-com/hyperframes).

This project is authored as a HyperFrames composition rather than a traditional React or Next.js website. The result is a motion-first portfolio that presents experience, projects, achievements, and contact details as timed visual scenes.

## Tech Stack

### Core authoring stack
- **HyperFrames** for composition structure, scene timing, preview, inspection, and validation
- **HTML5** for composition markup and scene structure
- **CSS3** for visual system, layout, and styling
- **Vanilla JavaScript** for runtime scene logic
- **GSAP 3.14** for animation timelines and transitions

### Design system
- **Space Grotesk** for display typography
- **IBM Plex Mono** for technical labels, metadata, and stats
- Custom visual direction defined in [`DESIGN.md`](./DESIGN.md)

### Tooling used
- **Node.js / npx** to run HyperFrames commands
- **Git + GitHub** for version control and hosting
- **HyperFrames CLI** commands used during development:
  - `npx hyperframes preview`
  - `npx hyperframes lint`
  - `npx hyperframes inspect`
  - `npx hyperframes validate`

## Project Structure

```text
portfolio-akshay/
├── index.html
├── hyperframes.json
├── DESIGN.md
├── SCRIPT.md
├── STORYBOARD.md
├── compositions/
│   ├── shell.html
│   ├── transitions.html
│   ├── hero.html
│   ├── impact.html
│   ├── experience.html
│   ├── projects.html
│   ├── credentials.html
│   └── contact.html
└── meta.json
```

## Scenes

- **Hero**: identity, positioning, and proof points
- **Impact**: delivery metrics and measurable outcomes
- **Experience**: timeline of roles and responsibilities
- **Projects**: flagship AI/ML systems
- **Credentials**: awards, publications, certifications, and stack
- **Contact**: closing statement and contact details

## Local Development

### Preview locally
```bash
npx hyperframes preview
```

### Lint the composition
```bash
npx hyperframes lint
```

### Inspect layout issues
```bash
npx hyperframes inspect --samples 10
```

### Validate runtime behavior
```bash
npx hyperframes validate
```

## Can this be deployed on GitHub Pages?

**Yes, but with one important caveat:** GitHub Pages can host this project because it is a static hosting platform for HTML, CSS, and JavaScript, and GitHub supports publishing from a branch or a GitHub Actions workflow. See the official docs: [What is GitHub Pages?](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages) and [Configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

### What works
- Hosting a **static playback version** of this portfolio
- Hosting a **wrapper page** that loads the HyperFrames composition through [`@hyperframes/player`](https://github.com/heygen-com/hyperframes/tree/main/packages/player)
- Publishing through a branch or GitHub Actions

### What does not work on GitHub Pages
- `hyperframes preview`
- `hyperframes render`
- `hyperframes inspect`
- `hyperframes validate`

Those are development/runtime tooling commands and must run locally or in CI, not inside GitHub Pages.

### Important architecture note
The files in this repo are **HyperFrames source compositions**, not a normal static website app. For GitHub Pages, the best approach is:

1. Keep this repo as the **source project**
2. Create a small **player wrapper page**
3. Load the composition using `<hyperframes-player src="./index.html" controls></hyperframes-player>`
4. Publish that wrapper page and composition files as a static site

### Best deployment options
- **GitHub Pages**: good for static interactive playback with a wrapper page
- **Vercel / Netlify**: also good for static playback and a bit easier to customize
- **Rendered MP4/WebM**: best if you want a guaranteed identical viewing experience everywhere

## Recommended Next Step for Deployment

If you want this portfolio live on GitHub Pages, the next step is to add:
- a small `index.html` or `viewer.html` wrapper using `@hyperframes/player`
- optional `.nojekyll`
- a GitHub Pages publishing setup

## Repository

GitHub repository:
- [akshayram1/portfolio-akshay](https://github.com/akshayram1/hyperframe_portfolio)
