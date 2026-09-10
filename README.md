# Styleo

Styleo is a responsive beauty-services discovery and booking prototype for clients in Accra, Ghana. It helps visitors browse beauty professionals, filter services, inspect professional profiles, and walk through an appointment-booking flow.

This project is a static website built with plain HTML, CSS, and JavaScript. It can be hosted directly with GitHub Pages without a server or build step.

## Live Features

- Responsive desktop, tablet, and mobile layout
- Hero search for beauty services
- Service categories for hair, makeup, nails, skincare, spa, barber, lashes, and massage
- Professional cards with ratings, reviews, location, distance, pricing, and verification status
- Sorting by recommended, rating, distance, price, and popularity
- Search and category filtering
- Saved/favorite professional interaction for the current browser session
- Professional profile modal with services and opening hours
- Multi-step appointment flow:
  - Select a service
  - Select a date
  - Select a time
  - Enter contact details
  - Review and confirm
- Mobile navigation menu
- Responsive image presentation and reveal animations
- Reduced-motion support for users who prefer less animation

## Technology

- HTML5
- CSS3 with responsive media queries, CSS variables, gradients, glass-style surfaces, and animations
- Vanilla JavaScript using DOM event listeners and in-memory state
- Google Fonts: Fraunces and Manrope
- Local JPG images stored in `IMAGES/`
- No npm packages, framework, compiler, or backend required

## Project Structure

```text
STYLEO/
|-- index.html                         GitHub Pages entry point
|-- styleo (2).html                    Original working HTML file
|-- README.md                           Project and deployment documentation
|-- IMAGES/                             Images used by the website
|   |-- download (1).jpg
|   |-- download (2).jpg
|   |-- download (3).jpg
|   |-- makeup artist model.jpg
|   |-- ...
|-- assets/                             Additional design/export assets
|-- styleo/                             Earlier project copy and supporting files
```

GitHub Pages only needs `index.html` and `IMAGES/` for the current page. The `assets/` and `styleo/` folders can remain in the repository for reference, or be removed later after confirming that no other page uses them.

## Run Locally

No installation is required.

### Option 1: Open the file

Double-click `index.html` and open it in a modern browser.

### Option 2: Use a local server

A local server gives more realistic hosting behavior. From the project folder, run one of these commands:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

If Python is not installed, use the Live Server extension in VS Code and open `index.html` with **Open with Live Server**.

## Publish with GitHub Pages

### Method A: Upload through the GitHub website

1. Sign in to [GitHub](https://github.com/).
2. Select **New repository**.
3. Give the repository a name such as `styleo`.
4. Choose **Public** if you want GitHub Pages on the free plan.
5. Create the repository.
6. Select **Add file > Upload files**.
7. Upload `index.html`, the `IMAGES` folder, and this `README.md`.
8. Select **Commit changes**.
9. Open the repository's **Settings** tab.
10. Select **Pages** in the left sidebar.
11. Under **Build and deployment**, choose **Deploy from a branch**.
12. Select the `main` branch and the `/ (root)` folder.
13. Select **Save**.
14. Wait for GitHub to finish publishing. The site URL will be shown in the Pages settings and normally looks like:

```text
https://YOUR-USERNAME.github.io/REPOSITORY-NAME/
```

### Method B: Publish with Git from PowerShell

Run these commands from the `STYLEO` folder after creating an empty GitHub repository:

```bash
git init
git add index.html IMAGES README.md
git commit -m "Publish Styleo website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

Replace `YOUR-USERNAME` and `YOUR-REPOSITORY` with your GitHub account and repository name. Then enable Pages using the Settings > Pages steps above.

For future changes:

```bash
git add .
git commit -m "Update Styleo website"
git push
```

### Project-site URL details

If the repository is named `styleo`, the default URL is:

```text
https://YOUR-USERNAME.github.io/styleo/
```

If you create a repository named exactly `YOUR-USERNAME.github.io`, it becomes your account's root site:

```text
https://YOUR-USERNAME.github.io/
```

## Important Hosting Notes

- Keep the file name exactly `index.html`; GitHub Pages looks for this entry file at the published root.
- Keep the `IMAGES` folder beside `index.html`. Image paths are relative and case-sensitive on GitHub's Linux servers.
- Do not rename `IMAGES` to `images` unless you also update every reference in the HTML and JavaScript.
- The page uses Google Fonts from `fonts.googleapis.com`; typography falls back gracefully if external fonts are unavailable.
- Asset filenames contain spaces, an emoji, and an en dash. The current page encodes these paths in JavaScript and HTML, but simpler filenames are recommended for future assets.
- GitHub Pages is static hosting. It cannot execute server-side code, store bookings, send email, authenticate users, or process payments by itself.

## Current Prototype Limitations

The following interactions are front-end demonstrations and do not persist data:

- Appointment confirmation does not create a real booking.
- Login and sign-up buttons do not have authentication behind them.
- Favorites are held only in memory and disappear after a page refresh.
- Search and professional records are hard-coded in `index.html`.
- The location field is visual only; it does not call a maps or geolocation service.
- App Store and Google Play buttons do not link to published applications.
- Footer links currently use placeholder `#` targets.
- The booking confirmation text says an email was sent, but no email is actually sent.

## Customizing the Website

### Add or edit professionals

Find the `PROFESSIONALS` array in `index.html`. Each professional includes an ID, name, area, rating, tags, image paths, opening hours, description, and services.

### Add a category

Update the `CATEGORIES` array and add a matching tag to at least one professional in `PROFESSIONALS`.

### Replace images

1. Add the new image inside `IMAGES/`.
2. Update the relevant filename in the HTML or in the JavaScript data arrays.
3. Use URL-safe filenames without spaces where possible.
4. Confirm the image path works on GitHub Pages after publishing.

### Connect a real backend

For a production booking service, replace the in-memory JavaScript state with an API and database. You will need user authentication, professional availability, booking conflict checks, secure server-side validation, email or SMS notifications, payment handling if required, and a privacy policy that matches the data you collect.

## Recommended Pre-Publish Checklist

- Confirm `index.html` opens correctly.
- Test the search, category filters, sorting, profile modal, and booking flow.
- Test at a narrow mobile width and a desktop width.
- Check that all images load without broken-image icons.
- Replace placeholder footer and app links.
- Add real business contact information.
- Review image licenses and confirm that you have permission to publish every image.
- Add a privacy policy and terms before collecting real customer information.
- Add a real backend before describing bookings as confirmed.

## License and Content

No license is currently declared for this project. Add a license file before accepting outside contributions or redistributing the code. Also verify the publication rights for all image assets and external fonts.

## Support

For GitHub Pages issues, check the repository's **Actions** tab for deployment errors and the **Settings > Pages** panel for the published URL. Most problems with this project will be caused by a missing `index.html`, an incorrectly uploaded `IMAGES` folder, or a filename/path mismatch.
