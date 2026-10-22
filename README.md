# Ronalyn B. Gonzaga | BSIT Student Portfolio

A responsive, single-page personal portfolio for Ronalyn B. Gonzaga, a Bachelor of Science in Information Technology student focused on web and software development. It is built with plain HTML, CSS, and JavaScript, with no frameworks, build tools, or dependencies to install.

## Features

- **Single-file site:** all HTML, CSS, JavaScript, and images live in `index.html`.
- **Seven sections:** Home, About, Skills, Experience, Projects, Education, and Contact.
- **Animated hero:** typing effect on the role line, a color-shifting name, and a floating profile card.
- **Interactive background:** a particle canvas with a glow that follows the cursor.
- **Scrolling tech band:** a seamless marquee of tools and working skills.
- **Project image viewer:** a lightbox (native `<dialog>`) for project screenshots.
- **Navigation extras:** sticky header with active-section highlighting, mobile menu, reading-progress bar, and a back-to-top button.
- **Accessible by design:** skip link, semantic landmarks, ARIA labels, visible focus states, and full support for `prefers-reduced-motion`.
- **Responsive:** layouts adapt for desktop, tablet, and mobile screens.

## Sections and Projects

| Section | What it shows |
| --- | --- |
| Home | Name, animated role line, short intro, and calls to action |
| About | Background, interests, and career goal |
| Skills | Technical skills (HTML5, CSS3, JavaScript, Git, GitHub, VS Code) and professional skills |
| Experience | Project-based experience timeline |
| Projects | Project cards with screenshots |
| Education | College, senior high, junior high, and elementary |
| Contact | Email and GitHub links |

Featured projects:

- **CarRent:** a multi-page car rental website with a dark, modern interface.
- **LectraAI:** an AI voice lecture generator that turns learning modules into audio, including its logo and mascot branding.
- **Monster Hunt: Love Beyond the Crown:** a fantasy story game with a custom title screen and visual identity.

## Tech Stack

- HTML5
- CSS3 (custom properties, grid, flexbox, `backdrop-filter`, scroll-driven effects)
- Vanilla JavaScript (IntersectionObserver, Canvas API, `<dialog>`)
- Google Fonts: [Inter](https://fonts.google.com/specimen/Inter) and [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (loaded from the web; the site falls back to system fonts offline)

## Getting Started

No installation is needed.

1. Download or clone this repository.
2. Open `index.html` in any modern browser (Chrome, Edge, Firefox, or Safari).

To preview with a local server instead:

```bash
# Python
python -m http.server 8000

# or Node
npx serve
```

Then visit `http://localhost:8000`.

## Project Structure

```
.
├── index.html   # The complete site: markup, styles, scripts, and embedded images
└── README.md
```

## Customizing

- **Colors, fonts, and spacing:** edit the design tokens in the `:root` blocks at the top of the `<style>` section. The later "THEME v3" block holds the current purple, pink, and orange palette.
- **Add a skill:** copy one `<li class="chip">` line into the right list in the Skills section.
- **Add a project:** copy an existing `<article class="card project">` block in the Projects section and update the image, text, and email subject.
- **Link a live demo or repository:** when a project has a real URL, add a button inside its `.project-actions`, as shown in the comment above the Projects section:

  ```html
  <a class="btn btn-secondary btn-sm" href="YOUR-REAL-URL" target="_blank" rel="noopener noreferrer">Live Demo</a>
  ```

  Replace `YOUR-REAL-URL` with the actual link. Do not publish the example as written.
- **Typing animation text:** change the `words` array in the "Typing animation" script near the bottom of the file.

## Deployment

Because the site is a single static file, it can be hosted for free on:

- [GitHub Pages](https://pages.github.com/)
- [Netlify](https://www.netlify.com/)
- [Vercel](https://vercel.com/)

For GitHub Pages: push the repository, go to **Settings → Pages**, choose the main branch as the source, and save.

## Browser Support

Works in current versions of Chrome, Edge, Firefox, and Safari. Features such as `<dialog>`, `backdrop-filter`, and `IntersectionObserver` are used with fallbacks where practical.

## AI Tools and Personalization Note

I used ChatGPT and Claude AI to help me plan, improve, and refine my portfolio website. I used their suggestions for website structure, design, grammar, and code improvements. I personalized the website by adding my own information, educational background, skills, and projects. I also reviewed and tested the website to make sure it reflects my identity and learning journey as an IT student.

## Contact

- **Email:** gonzagaronal6@gmail.com
- **GitHub:** [github.com/ronalyn123R](https://github.com/ronalyn123R)

## License

&copy; 2026 Ronalyn B. Gonzaga. All rights reserved.
