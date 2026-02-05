# DMI Portfolio Website (Static HTML/CSS)

This repository contains a clean, professional-looking **static portfolio website** used in **DevOps Micro Internship (DMI)** Week 1 to practice:
- Linux basics
- Nginx hosting
- Deployment proof / ownership
- Production-style checks

✅ Students deploy this website on an Ubuntu VM using Nginx and keep it live for 24 hours.

---

## Who is this for?
- DMI students (beginner → intermediate)
- Anyone learning how to host a static site with Nginx on Linux

---

## What you will build
A portfolio-style website hosted on:
- **Ubuntu VM**
- **Nginx**
- Accessible via: `http://<public-ip>`

---

## Mandatory Ownership Proof (DMI Rule)
Before you deploy, you MUST edit the footer and add your details:

Original:

```html
<p>Crafted with <span>cloud</span> excellence by Pravin Mishra</p>
```

Add this line (example):

```html
<p><strong>Deployed by:</strong> DMI Cohort 2 | Rahul Sharma | Group 4 | Week 1 | 16-01-2026</p>
```

✅ This proof must be visible in your browser screenshot submission.
## Notes on How to add Dynamic Date
# Footer Implementation

This document describes the footer requirements and explains how the deployment date is generated and displayed.

---

## Footer Requirements
The footer must display the following information:

- Application version  
- Deployment date  
- Author name  

These details provide visibility into the application version and deployment timeline.

---

## Deployment Date Generation

The deployment date is generated dynamically using JavaScript. This approach removes the need for manual updates and ensures the date is always current.

---

## HTML Implementation

A `<span>` element with a unique ID is used as a placeholder for the deployment date.

```html
<span id="deployDate"></span>

The script runs after the page content has fully loaded. It retrieves the current system date, formats it, and inserts it into the footer.

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const date = new Date();
    const day = date.getDate();
    const month = date.toLocaleString('default', { month: 'long' });
    const year = date.getFullYear();

    document.getElementById('deployDate').textContent =
      `${day} ${month} ${year}`;
  });
</script>

# Date Format
The deployment date is displayed in the following format:
DD Month YYYY

## Notes

- The date is based on the user’s system time.
- No external libraries are required.
- The script can be placed in the `<head>` section or just before the closing `</body>` tag.

## Notes on Footer Ammendments
- Improved footer font hierarchy (headings, links, meta text) for readability.
- Increased padding and standardized spacing with consistent gaps and removed default paragraph margins.
- Improved contrast by using a darker background and higher-contrast text/link colors.
- Tested responsive layout in:
  - Desktop view (normal width)
  - Mobile view (narrow viewport using DevTools)
