# Portfolio Site: Project Context

Personal portfolio for Gusti (rendered "Gústi" in Icelandic presentation contexts), final-year CS student at Háskólinn í Reykjavík (HR). The site is shared alongside a CV when applying for software engineering and customer service roles. It needs to ship soon, look clean, and be easy to update.

## Stack

- **Framework:** Astro with TypeScript (strict mode)
- **Content:** Astro content collections for `projects` and `blog`, written in Markdown
- **Styling:** Minimal and clean. Keep CSS straightforward, no heavy UI framework. Owner will customize visuals.
- **Hosting:** Vercel (static deploy)
- **Repo:** GitHub, deploys auto-trigger from `main`

## Site Structure

Four pages in the nav:

1. `/` (Home): short hook, intro, 2 to 3 featured projects, links to CV, GitHub, LinkedIn.
2. `/about` (About): SAR with Björgunarsveit Hafnarfjarðar, HR college life, running.
3. `/projects` (Projects list) and `/projects/[slug]` for per-project detail pages from the content collection.
4. `/blog` (Blog list) and `/blog/[slug]` for posts from the content collection. May stay empty at launch, but should work.

Footer on every page: GitHub, LinkedIn, email, and a visible "Download CV" link (PDF lives at `public/cv.pdf`).

The flagship project is the Advania thesis: a multi-agent Executive Summary pipeline built in Microsoft Copilot Studio and Power Automate. Treat that page as the most important project page when wiring up examples.

## Conventions

- **TypeScript strict mode.** Avoid `any` unless there's a real reason.
- **Idiomatic Astro.** Prefer plain `.astro` components and content collections over adding heavy dependencies.
- **File organization:** components in `src/components/`, layouts in `src/layouts/`, content in `src/content/`, page routes in `src/pages/`.
- **Accessibility basics:** semantic HTML, alt text on images, decent color contrast.
- **No client-side JS by default.** Add `client:*` directives only when an island actually needs interactivity.

## Writing and Tone

For any copy generated (page text, project descriptions, blog drafts):

- Concise and clear. No filler phrases, no marketing fluff.
- Formal but human. English by default, Icelandic when asked.
- **No em dashes.** Use commas, periods, parentheses, or colons instead.
- Don't oversell. The work speaks for itself.

## Workflow

1. Scaffold the site and get it deploying to Vercel first, even if pages are mostly empty.
2. Then build out structure: layouts, header, footer, content collection schemas.
3. Then fill in real content (About page, Advania project write-up, and so on).
4. Keep commits small and descriptive.

## Ask before doing

- Adding any npm dependency.
- Changing the deploy target or build setup.
- Introducing a new design system, CSS framework, or component library.

## Notes

Astro is new to the owner, who has a React background and full-stack TypeScript experience. When introducing an Astro-specific pattern (e.g., content collections, image optimization, view transitions), briefly explain what it does. Stay practical, no long lectures.
