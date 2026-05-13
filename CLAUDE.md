# Asana Lightweight Web App

## Goal
A minimal, cross-browser web app to view and manage Asana tasks — designed to work on iPad, Kindle browser, and any modern browser.

## Hosting
GitHub Pages (static files only — no server-side code).

## Core Features
- Pull tasks from Asana API, sorted by due date ascending (oldest first)
- Each row: [ checkbox ] [ task name ~70% ] [ due date ] [ +1 day button ]
- Checking the checkbox marks the task complete in Asana
- The +1 day button pushes the due date forward by one day in Asana

## Technical Constraints
- Pure HTML/CSS/JS — no build tools, no frameworks
- Must work in lightweight/older browsers (Kindle Silk, iPad Safari, etc.)
- Asana API is called directly from the browser (CORS is supported by Asana)
- Auth via Personal Access Token (PAT) stored in localStorage — user enters it once

## Asana API
- Base URL: https://app.asana.com/api/1.0
- Auth: Bearer token (PAT)
- Tasks endpoint: GET /tasks with assignee=me, workspace=<id>, opt_fields as needed

## Confirmed Decisions
- Tasks: all assigned across all projects (filtered to project below)
- Workspace ID: 1201435508588371
- Project ID: 1201435555554967
- Auth: PAT stored in localStorage — user enters once
- On complete: fade out and remove (2s fade animation)
- Tasks without due dates: hidden
- Hosting: GitHub Pages (single index.html, no build step)
