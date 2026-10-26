# Claude Code Plan: Minimalist Monochrome Multimedia & IT Portfolio

## 1. Project Goal

Build a personal portfolio website using **HTML and CSS only**. The
design should be minimalist, monochrome, editorial, and image-led,
inspired by the uploaded portfolio screenshots: a dark background,
restrained typography, generous negative space, a project-library
layout, and a persistent/simple navigation system.

The website presents **Aro** as: - A multimedia creative interested in
photography, videography, and sound technology for production. - A BS
Information Technology (BSIT) student who also builds IT/software
projects.

**Important constraint:** Do not use JavaScript, frameworks, libraries,
build tools, or a CSS framework. Use semantic HTML and plain CSS. Where
interaction is needed, prefer native HTML and CSS-only patterns such as
`<details>` / `<summary>`, anchor links, and CSS lightbox-style layouts.
Make clear in the code comments that a contact form cannot actually send
messages without a backend or a form service.

## 2. Technology and File Structure

Create a simple, editable project structure:

``` text
aro-portfolio/
├── index.html
├── style.css
├── plan.md
└── assets/
    ├── images/
    │   ├── profile-placeholder.jpg
    │   ├── project-placeholder-01.jpg
    │   ├── project-placeholder-02.jpg
    │   └── ...
    └── videos/
        └── video-placeholder.mp4
```

-   `index.html`: all page sections and content.
-   `style.css`: all styling, responsive rules, CSS-only interactions,
    and focus states.
-   `plan.md`: this implementation plan.
-   `assets/`: local images and videos. Use clearly named placeholders
    until real media is supplied.
-   Do not embed base64 images or use external libraries.
-   Use descriptive HTML comments around sections that the owner is
    expected to edit.

## 3. Visual Direction

### Theme

-   Monochrome palette: near-black/charcoal background, white text,
    muted gray secondary text, subtle gray borders.
-   Avoid bright accent colors, gradients, heavy shadows, and decorative
    effects.
-   Editorial typography with a strong, oversized landing-page headline
    and small, understated metadata.
-   Generous spacing and negative space.
-   Clean grid layouts, subtle hover transitions, and consistent image
    ratios.
-   Use system fonts or a sensible system-font stack; do not import
    external fonts.
-   Keep the design polished and responsive on desktop, tablet, and
    mobile.

### Reference screenshots

Use the uploaded screenshots as **visual inspiration only**: - Dark
charcoal/black background. - Simple left-aligned identity and category
navigation. - Project tiles presented like a visual archive or album. -
Project detail views with a title, description, and embedded media. - Do
not copy the reference website's exact branding, text, or assets.

## 4. Global Navigation

Create a top navigation bar.

-   **Left:** `Aro` --- links to the landing/home section.
-   **Middle:** `Projects`, `Experience`, `Contact` --- centered as a
    group on desktop.
-   Keep the navigation minimal and readable.
-   Use anchor links to navigate to sections on the same page.
-   Add a clear active/hover style using CSS. Since there is no
    JavaScript, do not claim to detect the currently visible section
    dynamically.
-   On mobile, allow the navigation to wrap or become a compact stacked
    layout without requiring JavaScript.
-   Include visible keyboard focus states.

Navigation labels and links must be easy to change in `index.html`.

## 5. Landing Page / Home

Create a visually strong hero section that introduces Aro.

### Required content

-   Name: `Aro`
-   Role line: `Multimedia Creative · BS Information Technology Student`
-   Main introduction, editable placeholder copy: \> I explore stories
    through photography, video, and sound, while building my technical
    foundation as a BSIT student.
-   Mention interests in:
    -   Photography
    -   Videography
    -   Sound technology for production
    -   Information Technology / software and technical projects
-   Add a simple text link or button-style link: `Explore Projects` →
    Projects section.
-   Optional small status line:
    `[Based in / Available for opportunities — edit this text]`.
-   Do not invent awards, years of professional experience, clients, or
    credentials.

### Layout

-   Use a large typographic introduction.
-   Include an optional portrait or creative-work image using a
    placeholder path and useful `alt` text.
-   Make the hero work even if the optional image is removed.
-   The first viewport should communicate both the creative and IT sides
    without feeling crowded.

## 6. Projects Section

The Projects section should feel like a **library, archive, or album**.
Use a two-column desktop layout where practical.

### Desktop layout

**Left sidebar:** project categories and editable project links. **Main
content:** project cards displayed in a responsive grid.

Sidebar content:

``` text
MULTIMEDIA

Photos
- [Photo Project Title 01]
- [Photo Project Title 02]
- [Photo Project Title 03]

Promotion Videos
- [Promotion Video Project Title 01]
- [Promotion Video Project Title 02]

Reels / Highlights
- [Reel or Highlight Project Title 01]
- [Reel or Highlight Project Title 02]

Films
- [Film Project Title 01]
- [Film Project Title 02]

IT PROJECTS
- MyFairview
- EcoTumbler
- Glassify
```

All project names above must be treated as editable placeholders or
user-supplied project names. Do not invent project descriptions or claim
features that have not been provided. Add comments in HTML showing where
to update project titles, summaries, dates, image paths, video paths,
and links.

### Project cards

Each card should include: - Thumbnail image or a CSS placeholder
block. - Project title. - Category label (`Photo`, `Promotion Video`,
`Reel / Highlight`, `Film`, or `IT Project`). - Optional year / role /
short summary, each with placeholder text. - A clear affordance that the
card can be opened.

Use a consistent image ratio and `object-fit: cover`. Add subtle hover
states without making the interface flashy.

### CSS-only project detail interaction

No JavaScript is allowed. Use native `<details>` and `<summary>` for
expandable project cards or project detail panels. Style `<summary>` to
look like a card, remove default markers where appropriate, and provide
a custom CSS indicator such as `+` / `−`.

When a project is opened, show a detail panel with the relevant content
type. Keep the markup accessible and keyboard-operable.

#### A. Photos

Interaction path:
`Photos category → project card → project detail with photo gallery and descriptions`

Detail content: - Project title. - `[Project overview / context]` -
`[My role]` - `[Date or year]` - One or more images using local
placeholder paths. - A short caption or description for each photo. -
Meaningful `alt` text placeholders to replace when images are added.

#### B. Films, Promotion Videos, Reels / Highlights

Interaction path:
`Category → project card → project detail with video and description`

Detail content: - Project title. - `[Project overview / context]` -
`[My role / responsibilities]` - `[Date or year]` - A native HTML
`<video controls>` element using a placeholder local video file, or an
editable embed-link placeholder if a video is hosted elsewhere. - Video
poster placeholder where useful. - A short description below the video.

If using a hosted video platform, include a clearly marked placeholder
for the embed URL. Do not invent working video URLs.

#### C. IT Projects

Include cards for: - **MyFairview** - **EcoTumbler** - **Glassify**

Each expandable detail panel should have placeholders for: - Project
summary. - Problem addressed. - Technologies used. - My role /
contribution. - Screenshots or diagrams. - Repository or live-demo link.

Do not make up project functionality, stack details, or repository
links. Use `[Add details]` placeholders until supplied.

### Category filtering limitation

Because this is HTML/CSS only, do not implement JavaScript-based dynamic
filtering. Instead, use: - Sidebar anchor links to category sections,
and/or - Separate category sections with their own project grids. -
Optional CSS-only radio-button filtering only if it can be implemented
accessibly and without JavaScript.

Prefer simple category anchors and clearly separated category grids for
maintainability and accessibility.

## 7. Experience Section

This section should resemble a clean resume, with **Multimedia as the
primary focus** and **BSIT / technical skills as secondary**.

### A. Skills first

Show the skills section before experience entries.

#### Multimedia --- Primary

Use editable skill labels or grouped lists such as: - Photography ---
`[Add specific skills / equipment]` - Videography ---
`[Add camera, framing, or shooting skills]` - Video Editing ---
`[Add editing tools and techniques]` - Sound Technology / Production
Audio --- `[Add recording, mixing, or audio setup skills]` - Production
Support --- `[Add relevant responsibilities]`

Only retain skills that are accurate. Keep all bracketed content
editable.

#### Information Technology --- Secondary

Use editable entries such as: - Programming --- `[Add languages]` - Web
/ App Development --- `[Add technologies]` - IT Support &
Troubleshooting --- `[Add relevant skills]` - Hardware / Software ---
`[Add relevant skills]` - Tools --- `[Add tools actually used]`

Do not automatically claim proficiency levels. If proficiency labels are
included, leave them as editable placeholders.

### B. Experience / Activities

Use a resume-style list or timeline. Each entry should have: -
`[Role / Position]` - `[Organization / Project]` - `[Dates]` -
`[Location, optional]` - 2--4 concise bullets for responsibilities,
contributions, or outcomes.

Include one example template entry clearly labeled as a placeholder. Do
not invent employment, client, production, or volunteer history.

### C. Education

Include an editable education entry: -
`Bachelor of Science in Information Technology (BSIT)` -
`[School name]` - `[Expected graduation year]` -
`[Relevant coursework or activities — optional]`

Do not assume the school name or change the graduation date unless
supplied in the page content.

## 8. Contact Section

Create a clean contact section with direct contact details and a simple
contact form.

### Contact links

-   Email: `[your-email@example.com]`
    -   Use `mailto:` with the placeholder email until the real address
        is entered.
-   LinkedIn: `[Your LinkedIn profile URL]`
    -   Use a clearly marked placeholder link until the correct URL is
        provided.
-   Optional: `[Other relevant portfolio or social link]`.

Do not invent an email address or LinkedIn URL.

### Contact form

Fields: - Name - Email - Subject - Message - Submit button

Requirements: - Use semantic `<form>`, `<label>`, `<input>`, and
`<textarea>` elements. - Include `required` where appropriate and
suitable input types. - Ensure labels are visible and associated with
their fields. - Style the form to match the monochrome theme. - Use a
placeholder `action` / submission setup and a code comment explaining
that the form will not send messages until connected to a backend or
form service. - Do not show a fake "message sent" success state. Do not
use JavaScript.

## 9. Responsive and Accessibility Requirements

-   Use semantic HTML5 elements: `header`, `nav`, `main`, `section`,
    `article`, `aside`, `footer`.
-   Include a skip link to the main content.
-   Provide descriptive image `alt` attributes.
-   Maintain readable contrast between text and background.
-   Ensure all links and `<summary>` controls are keyboard-accessible.
-   Add visible `:focus-visible` styles.
-   Use responsive CSS with media queries for tablet and mobile.
-   Avoid horizontal scrolling at common viewport widths.
-   Respect `prefers-reduced-motion` by reducing or removing
    transitions.
-   Avoid using color alone to communicate interaction.
-   Use CSS custom properties for colors, spacing, and typography so the
    theme can be edited from one place.

## 10. Placeholder and Editing Rules

**Every page section and every content item must be easy to modify.**

-   Use clear placeholder copy such as `[Add project description]`,
    `[Add year]`, `[Add role]`, `[Add image path]`, `[Add email]`, and
    `[Add LinkedIn URL]`.
-   Add HTML comments before major blocks explaining what to replace.
-   Use descriptive class names.
-   Avoid duplicating complex styles; use reusable card and section
    classes.
-   Keep content in straightforward HTML rather than generating it
    dynamically.
-   Do not fabricate achievements, project details, client names, work
    experience, contact information, or media links.
-   The supplied IT project names `MyFairview`, `EcoTumbler`, and
    `Glassify` should be included exactly as written.

## 11. Suggested Design Tokens

Set up CSS custom properties in `:root`, for example:

``` css
:root {
  --color-bg: #202020;
  --color-surface: #262626;
  --color-text: #f4f4f4;
  --color-muted: #a2a2a2;
  --color-border: #414141;
  --color-hover: #ffffff;

  --font-body: Arial, Helvetica, sans-serif;
  --font-display: Arial, Helvetica, sans-serif;

  --space-1: 0.5rem;
  --space-2: 1rem;
  --space-3: 1.5rem;
  --space-4: 2rem;
  --space-5: 3rem;
  --space-6: 5rem;

  --content-width: 1200px;
}
```

These are starting values, not fixed requirements. Keep the palette
monochrome and make it easy to adjust.

## 12. Implementation Steps for Claude Code

1.  Inspect the current project directory before creating files.
    Preserve any existing work that is relevant.
2.  Create or update `plan.md` with this plan.
3.  Build `index.html` with all page sections and placeholders.
4.  Build `style.css` with the monochrome design, responsive layouts,
    and CSS-only interactions.
5.  Add the project categories and cards, with `<details>` / `<summary>`
    panels for project details.
6.  Add the resume-like Experience section with Multimedia skills first
    and IT skills second.
7.  Add contact links and the non-functional-until-connected contact
    form.
8.  Add comments identifying all places where Aro can edit text, links,
    project details, and media.
9.  Validate the HTML structure, local file references, responsive
    behavior, focus states, and absence of JavaScript.
10. Summarize the files created and explain how to customize them.

## 13. Acceptance Checklist

-   [ ] Uses only HTML and CSS; no JavaScript.
-   [ ] Monochrome, minimalist, editorial visual style inspired by the
    uploaded references.
-   [ ] Top navigation: `Aro` on the left; `Projects`, `Experience`, and
    `Contact` grouped in the middle on desktop.
-   [ ] Landing page introduces multimedia interests and BSIT studies.
-   [ ] Projects area has a left-side category list and
    library/album-style cards.
-   [ ] Photo project details display images and descriptions.
-   [ ] Film/video/highlight details display a video player and
    description.
-   [ ] IT project cards include MyFairview, EcoTumbler, and Glassify.
-   [ ] Experience starts with Multimedia skills, followed by IT skills,
    then resume-style entries and education.
-   [ ] Contact includes editable email and LinkedIn placeholders plus a
    clearly labeled form.
-   [ ] All project titles, descriptions, dates, links, images, and
    videos are editable.
-   [ ] Responsive on desktop, tablet, and mobile.
-   [ ] Keyboard navigation and visible focus states work.
-   [ ] No invented credentials, projects, work history, or contact
    information.
-   [ ] Contact form does not falsely claim to send messages before it
    is connected to a backend or form service.

## 14. Final Instruction to Claude Code

Implement the website from this plan in the current project directory.
Keep the code beginner-friendly, readable, and easy to edit. Use only
plain HTML and CSS. Treat the uploaded screenshots as layout and mood
references, not as assets to copy. If real project images, descriptions,
video files, email, or LinkedIn details are not available, leave clearly
labeled placeholders rather than guessing.
