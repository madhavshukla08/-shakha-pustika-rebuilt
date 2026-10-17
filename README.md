# Shakha Pustika — Rebuilt Project

This package uses the actual `Shakha_Pustika-2.html` source recovered from your ChatGPT Library as the application entry point. It is not a claim that this is the unavailable `shakha-app-main.zip` repository; it is a runnable rebuild/package based on the actual Shakha Pustika source available here.

## Features in the included app

- Hindi and English interface
- Login gate with demo credentials
- Dashboard
- Member management
- Attendance recording and attendance history
- Games, Subhashitam, Amritvachan, Ganvesh and Pravas sections
- Shakha/organisation settings
- Responsive mobile navigation
- Browser storage persistence
- Optional Google Sign-In UI (requires a configured Google OAuth Client ID)

## Run locally

### Quickest method

Open `index.html` in a modern browser. Most features work without a build step.

### Recommended local web server

Python 3 is sufficient; no dependencies are required:

```bash
cd shakha-pustika-rebuilt
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Demo login

- Username: `demo`
- Passcode: `demo123`

Change this before any demonstration where real information is entered.

## Important limitations and security notes

- This is a static HTML/JavaScript application; it does **not** include a server, database, or production authentication backend.
- In standalone hosting, records are saved in the current browser's local storage. They are not automatically shared across devices or users, and clearing browser data may remove them.
- The included demo login is client-side and is not secure for protecting sensitive information. Do not use it as production authentication.
- Google sign-in will not work until `GOOGLE_CLIENT_ID` in `index.html` is replaced with a real OAuth Web Client ID and the deployed domain is added to its authorised origins. A real production app should verify credentials server-side.
- Google Fonts and the Google Identity script are external dependencies and require internet access.

## Static hosting

You can upload `index.html` to a static host (Netlify, Vercel, GitHub Pages, or any standard web server). The other files in this package are documentation and editor/deployment helpers.

## Project layout

```text
shakha-pustika-rebuilt/
├── index.html       # Actual recovered app source
├── README.md        # Setup, features and limitations
├── netlify.toml     # Static hosting configuration
├── vercel.json      # Static hosting configuration
└── .gitignore
```

## Production upgrade path

For secure multi-user use, replace client-side login/storage with a backend API and a database (for example, PostgreSQL), enforce server-side authorisation, hash passwords, add backups, and configure Google OAuth verification on the server. This package intentionally does not pretend those backend services already exist.
