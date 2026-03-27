# Systima

Static website for the `4ο Σύστημα Προσκόπων Νέας Σμύρνης`.

The project is a small multi-page HTML/CSS/JavaScript site in Greek with:

- a home page
- an about page for the scout group and age sections
- a contact page with phone, email, map, and contact form
- a thank-you page shown after form submission

## Project Structure

```text
Systima/
├── index.html
├── about.html
├── contact.html
├── thanks.html
├── css/
│   └── common.css
├── javascript/
│   └── common.js
└── images/
```

## Pages

- `index.html`: landing page and overview of the group
- `about.html`: history, section breakdown, and unit presentation
- `contact.html`: contact details, map embed, and message form
- `thanks.html`: confirmation page after successful form submission

## Frontend Behavior

Shared behavior lives in `javascript/common.js`.

It currently handles:

- mobile navigation open/close state
- auto-closing the menu on outside click or link click
- setting the contact form redirect URL dynamically
- calculating years of existence from `1960`

## Local Preview

Because this is a static site, you can open the HTML files directly in a browser.

For a cleaner local preview with consistent relative paths, run a simple local server from the project root:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Contact Form

The contact form in `contact.html` submits through [FormSubmit](https://formsubmit.co/).

Current behavior:

- form action posts to `https://formsubmit.co/rivertsamaidi@gmail.com`
- `_next` redirects users to `thanks.html`
- `common.js` converts that redirect to an absolute URL when the site is served over HTTP(S)

If the email destination changes, update the `action` value in `contact.html`.

## Assets and Dependencies

- Local styles are in `css/common.css`
- Local images are stored in `images/`
- Font Awesome icons are loaded from CDNJS
- Google Maps is embedded in `contact.html`

## Editing Notes

- Keep all page metadata in Greek unless there is a reason to expose English copy
- Reuse `css/common.css` and `javascript/common.js` for shared site behavior
- Preserve relative asset paths so the site works when hosted as plain static files
