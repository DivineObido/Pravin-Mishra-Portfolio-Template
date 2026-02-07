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

## Features

### Dynamic Deploy Date in Footer

The footer displays an automatically updated deployment date that shows the current date whenever the page is loaded.

#### Requirements
- Footer must display the last deployment date
- Date format: DD Mon YYYY (e.g., "07 Feb 2026")
- Date updates automatically without manual intervention

#### Implementation

The deploy date is generated using JavaScript and formatted in British English locale.

**HTML Structure:**
```html
<footer>
    <p>Last deployed: <span id="deployDate"></span></p>
</footer>
```

**JavaScript Code:**
```javascript
// Dynamic deploy date implementation
const today = new Date();
const options = { day: '2-digit', month: 'short', year: 'numeric' };
const formattedDate = today.toLocaleDateString('en-GB', options);
document.getElementById('deployDate').textContent = formattedDate;
```

#### How It Works
1. JavaScript creates a new `Date()` object representing the current date
2. The date is formatted using `toLocaleDateString()` with British English locale ('en-GB')
3. Format options specify: 2-digit day, short month name, and 4-digit year
4. The formatted date is inserted into the span element with ID `deployDate`
5. This ensures the footer always shows the current date when the page loads