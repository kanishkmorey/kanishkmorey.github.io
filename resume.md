---
# This layout (_layouts/resume.html) reads all the fields below — role,
# summary, experience, skills, education — and loops over them to build
# the page. To update your resume, edit this YAML; you shouldn't need to
# touch the layout file itself unless you want to change how it looks.
layout: resume
title: Resume
permalink: /resume/
resume_pdf: /assets/resume.pdf
# ^ NOTE: this file doesn't exist yet — add your actual resume PDF at
#   assets/resume.pdf so the "Download PDF" button on this page works.

role: "Back End Software Engineer"
summary: >-
  Backend engineer with about 14 months of professional experience
  building and maintaining APIs and backend services.

experience:
  - company: "Company Name"
    title: "Back End Software Engineer"
    period: "Month 20XX – Present"
    points:
      - "Describe a concrete system or service you own."
      - "Describe a specific outcome or improvement you drove."
  # Add more entries above this line as your history grows —
  # each one just needs company / title / period / points.

skills:
  - "Language / framework"
  - "Databases"
  - "Tooling"

education:
  - school: "Your College or University"
    degree: "Degree, Field"
    period: "20XX – 20XX"
---
