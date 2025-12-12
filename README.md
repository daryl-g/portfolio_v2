# Portfolio v2.0

Building upon my current portfolio hosted on Wordpress (v1.0), this version aims to be a front-end portfolio developed solely using TypeScript and Svelte while using the current Wordpress infrastructure for backend and content management (since I'm too lazy to build my own).

**Note to self**: tbf, there's actually not that much content to manage anyway, it is mostly media stuff like images and videos, the contents itself are backed into the actual page instead.

## Ideas

**Responsive/Mobile ver.**:
Recycle the layout of Portfolio v1.0 but adapt it to the new layout and design.

**Layout**:

- Static page that relies on no scrolling with animated background (most likely just gradient colour moving around to create atmosphere).
- Contain all contents within the 85% area from the centre of the page, remaining 15% from the borders are left blank intentionally.

**Home page**:

- Full screen, divided into two vertical sections (60-40 ratio).
- Left side: Retain the 'hello' part of the portfolio but make it a bit fancier.
  - Auto carousel of 'hello' in languages that I can speak (English, Vietnamese, German).
  - Name lights up like it's a neon adboard?
  - Potential CTA buttons (max 2).
- Right side: Slideshow for different types of past work/projects that links to their respective category page.

**Nav bar**:

- Potentially burger nav bar on the right side of the screen.

**Experiences page**:

- Mirror Football Manager's Manager Timeline.
- Horizontal timeline on wide screen, vertical timeline with basic details on vertical screen.
- Hover on each logo to display more details about past responsibilities.
- Tools/apps used for each job listed below main logo in mono logos.

**Work page**:

- Should change this to **Projects** instead.
- 4 categories at the top, with an example image as the background + transparent background + text on top.
  - When clicked, projects below change to all that are categorised under the selected category.
  - Also change the page route while does not give away that on the front-end.
- Gallery-style with title below each thumbnail, kinda like a museum/art gallery.
- Individual page:
  - Artifacts on the left, start with the demo video if there's any, potential width: 30-40%.
  - Description on the right, potential width: 60-70%.

**Wall of Inspirations**:

- Tempted to add this page to show who have inspired me throughout my journey so far.
- Similar gallery-inspired layout to the Work page but without any categories.
- Thumbnail of the person (only famous people) + one memorable quote below.
- Not really a significant priority rn, might not even be rolled out when the final v2.0.0 version is completed.

**Contact**:

- Probably a 50-50 ratio layout.
- Might not add a form due to potential bot spam that I don't care about.
- Social links + email can be here instead and on the right section.
- Message and CTA can be on the left.

## Inspo

Probably any Cyberpunk-themed or Tokyo Night-themed website I can find.

## Resources

- https://svelte.dev/docs/svelte/getting-started
- https://svelte.dev/docs/svelte/typescript

---

<div align="center">
[![Claude](https://img.shields.io/badge/Made%20with%20a%20lil%20Claude-da7756?style=flat-square&labelColor=da7756&logo=claude&logoColor=white)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
</div>
