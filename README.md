# Mummy-G (मम्मी-G)

**A maternal health website concept focused on supporting women across rural and urban India throughout pregnancy and after childbirth.**

## Live Demo

[https://mummy-ji.netlify.app/](https://mummy-ji.netlify.app)

## About the project

## About the project

Mummy-G presents a nonprofit maternal care initiative with the mission of empowering Indian women through better maternal health and safer deliveries. The website brings together information about the initiative, proposed services, a medical panel, pregnancy FAQs, and forms for appointments, community registration, donations, and enquiries.

The concept focuses on the physical and mental wellbeing of mothers and newborns, with particular attention to women in rural areas and those who face barriers to affordable care. Its service offerings describe nutrition and exercise support, medication and checkups, emergency assistance, transport, community meetups, and care after childbirth.

The repository currently contains a **frontend prototype**, with template PHP email handlers. The pages demonstrate the intended experience; registration, payments, and operational healthcare services are not implemented as complete systems.

## Contents

- [Features and pages](#features-and-pages)
- [Technology stack](#technology-stack)
- [How the project works](#how-the-project-works)
- [Project structure](#project-structure)
- [Running locally](#running-locally)
- [Current limitations](#current-limitations)
- [Deployment](#deployment)
- [Customization](#customization)
- [Future improvements](#future-improvements)
- [Contributing](#contributing)
- [Credits and licensing](#credits-and-licensing)
- [GitHub About section](#github-about-section)

## Features and pages

| Page or section | Purpose and current implementation |
| --- | --- |
| Home — `index.html` | Introduces the mission through a hero carousel, About section, counters, testimonials, doctor profiles, FAQs, and contact information |
| Appointment — home-page section | Form for name, email, phone, appointment date, department selections, doctor, and an optional message; targets `forms/appointment.php` |
| Services — `services.html` | Six service cards with icons and descriptions |
| Registration — `register.html` | Intake form for personal details, identity proof, blood group, health conditions, region, state, occupation, and pregnancy history |
| Donations — `donation.html` | Donor details, identity proof, address, payment-method selection, amount field, and submit/reset controls |
| Contact — `contact.html` | Standalone enquiry form, address, and Google Maps embed |
| Home-page contact form | Name, email, subject, and message fields; targets `forms/contact.php` |
| Newsletter — home-page footer | Email subscription form UI |
| Template page — `inner-page.html` | Retained Medicio example page for building additional pages |

### Services represented in the concept

- **Diet and exercise tracking:** nutrition and activity support during pregnancy.
- **Medication and regular checkups:** a proposed program of free medication and medical visits.
- **Emergency helpline:** a proposed channel for urgent healthcare and transportation assistance.
- **Transport availability:** support for travelling to checkups and during delivery.
- **Community meetups:** opportunities for pregnant women to share experiences and support their mental wellbeing.
- **Post-pregnancy care:** support for mothers and newborns after childbirth.

These are service descriptions in the website. The repository does not contain a working tracker, transport booking system, emergency dispatch integration, or healthcare service backend.

## Technology stack

| Technology | Role |
| --- | --- |
| HTML | Page structure, content, navigation, and forms |
| CSS | Main theme and individual styles for services, registration, donations, and contact |
| JavaScript | Navigation behavior, scrolling, carousel indicators, and initialization of UI libraries |
| Bootstrap | Main-page layout and components; the standalone contact page references Bootstrap 3.3.7 through a CDN |
| Animate.css and AOS | Animation styles and scroll-triggered effects |
| Bootstrap Icons, Boxicons, and Font Awesome | Icons used or referenced by the pages |
| AngularJS 1.6.4 | Loaded by the standalone contact page for its `ng-model` bindings |
| Swiper, GLightbox, and PureCounter | Referenced for sliders, lightboxes, and animated counters; required files are missing from the current local copy |
| PHP | Template email handlers for contact and appointment requests |
| Google Fonts and Google Maps | External fonts and embedded location maps |

There is no package manifest, dependency installation command, frontend build step, database, or application framework configuration in this project folder.

## How the project works

The site consists of static HTML pages. Home-page navigation connects visitors to registration, services, donation, and contact pages, while anchor links lead to sections such as About, Doctors, and Appointments.

The intended main-page interactions are initialized in `js/main.js`: mobile navigation, active links while scrolling, smooth scrolling, a back-to-top button, hero carousel indicators, sliders, animations, and counters. These interactions depend on the referenced libraries and correct asset paths.

The appointment and home-page contact forms POST to PHP handlers. Those handlers attempt to load the template's `PHP Email Form` library and email the submitted fields to a configured recipient. The library and a real receiving address still need to be supplied. The standalone registration, donation, contact, and newsletter forms have no configured submission backend.

## Project structure

```text
Mummy-G/
├── README.md                 # Project documentation
├── index.html                # Main maternal health landing page
├── services.html             # Service information
├── services.css              # Service-card styling
├── register.html             # New-user intake form
├── register.css              # Registration styling
├── donation.html             # Donation form UI
├── donation.css              # Donation styling
├── contact.html              # Standalone enquiry page
├── contact.css               # Contact-page styling
├── inner-page.html           # Retained Medicio example page
├── css/
│   └── style.css             # Main theme stylesheet
├── js/
│   └── main.js               # Main-page interactions
├── img/                      # Branding, slides, doctors, and gallery images
├── forms/
│   ├── appointment.php       # Template appointment email handler
│   ├── contact.php           # Template contact email handler
│   └── Readme.txt            # Form-library information
├── vendor/                   # Included third-party frontend assets
├── Readme.txt                # Original template attribution
└── changelog.txt             # Original template changelog
```

## Current limitations

The following observations are based on the files in this project folder:

- **Asset paths:** `index.html` and `inner-page.html` reference `assets/css/`, `assets/js/`, `assets/img/`, and `assets/vendor/`, but these folders currently sit directly at the project root. Align the references with the actual layout or organize the files under `assets/`.
- **Missing dependencies:** referenced local files for Swiper, GLightbox, PureCounter, Font Awesome, and the PHP email form validation script are absent. Restore compatible dependencies or remove their references and initialization code.
- **Missing stylesheet:** registration and donation pages reference `a3styles1.css`, which is not present.
- **Email handlers:** both PHP files depend on an unavailable library and use a placeholder recipient address.
- **Form persistence:** registration, donation, standalone contact, and newsletter forms are not connected to storage or a service. No authentication or account system is included.
- **Payments:** selecting UPI, net banking, or a card only selects a form option. There is no payment gateway or transaction processing.
- **Form markup:** repeated field IDs, placeholder option values, duplicate appointment field names, and the donation amount field's `email` input type need correction before real submissions.
- **Template content:** some titles, links, content, and metadata retain template defaults. Profiles, testimonials, counters, and contact details are static website content rather than verified operational data.
- **Verification:** no automated test suite is included. The demo URL is preserved from the original README; its current availability has not been verified.

## Customization

- Edit `index.html` for the mission, hero text, profiles, testimonials, FAQs, and contact details.
- Edit `services.html` for service descriptions.
- Update `register.html`, `donation.html`, and `contact.html` for form fields and submission behavior.
- Adjust `css/style.css` for the main theme and page-specific CSS files for standalone pages.
- Replace files in `img/` and update references when changing branding or imagery.
- Update `js/main.js` for navigation behavior or supported UI libraries.
- Preserve third-party attribution and review applicable terms when modifying the design.

## Future improvements

Possible next steps for turning the concept into a working application:

- Repair asset paths, restore dependencies, and replace template placeholders.
- Connect registration and appointments to a backend with validated data storage.
- Add appointment availability, confirmations, and staff workflows.
- Integrate a payment gateway and donation receipts.
- Implement the diet and exercise tracker described on the services page.
- Add Hindi and other regional-language content.
- Improve mobile layouts, keyboard navigation, form labels, and feedback messages.
- Review health information and service claims before presenting the site as an operational service.
- Add privacy controls appropriate to personal and health information.
- Add checks for links, asset loading, and form behavior.

These are proposed improvements, not existing functionality.


