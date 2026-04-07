# Courier Service Public Website

You are building a professional public website for a courier service company undergoing its first digital transformation. The project must be production-ready, visually polished, and meet all technical requirements below.

---

## Project Structure

Create the following files in the project root:

```
/
├── index.html        (landing page)
├── application.html  (application/sign-up form)
├── validation.js     (form validation logic)
└── styles.css        (only if Tailwind CDN is insufficient)
```

---

## Tech Stack

- Tailwind CSS via CDN (utility classes only — no custom CSS unless absolutely necessary)
- Vanilla JavaScript for form validation
- Semantic HTML5 throughout
- No frameworks, no build tools

---

## Landing Page — `index.html`

Build a professional landing page for a courier service company. Include:

1. `<header>` with company logo/name and `<nav>` with navigation links (Home, Services, About, Apply)
2. Hero `<section>` with a strong headline, value proposition, and a CTA button linking to `application.html`
3. At least two additional `<section>` elements — e.g., key services/features, why choose us, how it works
4. `<footer>` with contact information (phone, email, address)
5. A prominent link/button that directs users to the application form

### Design Requirements

- Mobile-first, fully responsive using Tailwind breakpoints: `sm:`, `md:`, `lg:`
- Visually professional and coherent — this is a company's digital debut
- All images must have descriptive `alt` attributes
- Use semantic tags throughout: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`
- Add ARIA attributes where appropriate (`aria-label`, `role`, `aria-describedby`)
- Include Schema.org JSON-LD in a `<script type="application/ld+json">` block using `LocalBusiness` or `Organization` type with real company fields (`name`, `url`, `telephone`, `address`, `description`)

---

## Application Form — `application.html`

Build a structured application/sign-up form for prospective courier drivers or clients (match the exact fields from your `CONTEXT.md`). Include:

- Personal information fieldset: full name, email (`type="email"`), phone (`type="tel"`), date of birth (`type="date"`)
- Service/role information fieldset: relevant fields from `CONTEXT.md` (vehicle type, availability, service area, experience, etc.)
- All fields must use `<label>` elements correctly associated via `for` attribute
- Group related fields with `<fieldset>` and `<legend>`
- Mark all required fields with the `required` attribute
- Submit button and a secondary "Clear Form" button
- Fully responsive form layout using Tailwind
- Focus states and error/success visual states styled with Tailwind

---

## Validation — `validation.js`

Implement client-side validation with these behaviors:

- **Real-time validation:** validate on `blur` (when user leaves a field) and on submit
- Prevent form submission if any field is invalid
- Display specific, helpful error messages per field (not generic "invalid field" messages)
- Style error states with a red border/text and success states with a green border
- Error messages must be accessible: use `aria-describedby` linking inputs to their error `<span>` elements, and set `aria-invalid="true"` on failing inputs
- Show a success message/banner when all validation passes (simulate submission — no backend needed)
- Clear button must reset all fields and all error/success states

### Validation Rules

| Field | Rule |
|---|---|
| Name | Required, minimum 2 characters, no numbers |
| Email | Required, valid email format |
| Phone | Required, valid phone number format |
| Date of birth | Required, must be 18+ years old |
| All other required fields | Non-empty validation with specific messages |
| Domain-specific fields | Any rules from `CONTEXT.md` (vehicle type, service zone, etc.) |

---

## Accessibility Requirements

- All interactive elements must be keyboard accessible (Tab, Enter, Space)
- Color contrast must meet WCAG AA minimum standards
- Navigation must be logical and predictable
- Error messages must be announced to screen readers via `aria-live` or `aria-describedby`
- No reliance on color alone to communicate state

---

## SEO Requirements

- `<title>` and `<meta name="description">` on every page
- Proper heading hierarchy (`h1` → `h2` → `h3`, no skipping)
- Schema.org JSON-LD block on `index.html`
- Open Graph meta tags (`og:title`, `og:description`, `og:type`)
- Semantic landmark regions on every page

---

## Quality Bar

- Zero unnecessary `<div>` wrappers where semantic tags apply
- No inline styles — Tailwind classes only
- No console errors
- Passes basic responsive check at 375px (mobile), 768px (tablet), 1280px (desktop)
- Professional enough to represent a real company's first digital presence

---

> **Important:** Before writing any code, read `CONTEXT.md`, `seo_geo.md`, and `web_fundamentals` completely. All field names, company details, domain-specific values, and validation constraints must match exactly what is defined there. A generic implementation that ignores the context will not pass evaluation.