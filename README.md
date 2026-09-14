# Vow Renewal & RSVP Experience — Prototype Feedback

A single-page feedback form for the low-fidelity vow renewal prototype review (Round 1).
Built from the `vow-renewal-prototype-feedback` brief — 39 questions across 9 sections.

**Prototype under review:** [figma.com/make/CM9PYIYY4DTGF8XFj3P7Oq](https://figma.com/make/CM9PYIYY4DTGF8XFj3P7Oq)

## Structure

```
vercel.json                              root URL → the form
vow_renewal_feedback/feedback.html       the whole form (no build step)
```

Plain HTML, CSS and JavaScript in one file. No dependencies beyond Google Fonts.

## The form

- **Tabbed sections** — one section at a time, sticky tab strip, Back/Next, `#section-x` deep links.
  Hidden sections stay in the DOM, so every answer submits regardless of which tab is open.
- **Reviewer capture** — name is required; email, role and review date are also collected.
  The name goes into the notification email subject, and the email into `_replyto`.
- **Rating scales** on Q2, Q17 and Q19; ranking on Q35 that won't let a number be used twice.
- **Copy change log** with repeatable rows.
- Responsive to 375px, and prints with all sections expanded.

## Submissions

Posts to Formspree. The endpoint is the `action` on the `<form>` in `feedback.html`.

> Currently pointing at form `xbdakjjj`, shared with the HWB questionnaire.
> Create a separate Formspree form and swap the `action` URL to split the inboxes.

## Deploying

Hosted on Vercel as a static site — no build command, no framework.
Pushing to `master` redeploys.
