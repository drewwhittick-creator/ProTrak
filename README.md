# ProTrak

A small, iPhone-style planner for prioritizing work projects. It ranks each project by **impact × urgency**, keeps a checklist of next steps, and shows how you're progressing over time.

It's a single HTML file with no build step. It syncs between devices through Firebase.

## Features

- **Focus list**: active projects ranked by impact × urgency, each showing its next step, which you can tick off right from the list.
- **Matrix view**: projects sorted into Do Now, Schedule, Quick Win and Later.
- **Size-aware priority**: each project has a size (Small, Medium, Large). Urgency compares the days left with the work the project needs, so a small task due in two weeks waits while a medium one due in four days moves up. Large projects you haven't touched in a couple of days get pulled into Do Now until you put time in. Each card shows the reason for its priority.
- **New-project quiz**: one question per screen (name, stakeholder, due date, size, impact, urgency, status, next steps), ending with a review screen.
- **Repeating tasks**: a Today checklist for tasks that repeat every day, on weekdays or weekly, with streaks. A task can be linked to a project so ticking it off counts as time spent.
- **Time tracking**: a "Spent Time on This Today" button in each project. Ticking off a step also counts. Cards show when you last worked on a project and flag ones untouched for 7+ days, and the All tab has a Neglected filter.
- **Project details**: next steps, stakeholder, due date, status and blockers, file location (with Open Link or Copy Location), and dated notes.
- **Completed Projects screen**: completion counts, average time to finish, on-time rate, steps per week, progress on open projects, weekly charts, and a button to clear completed projects.
- Light and dark mode, smooth transitions, and layouts that work on a phone and a laptop.

Live app: https://drewwhittick-creator.github.io/ProTrak/

## Running it

Open `index.html` in any modern browser. Nothing else is needed.

### Hosting on GitHub Pages

1. Create a new repository named `ProTrak` and upload `index.html` and `README.md` to the root.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then **Save**.
4. After a minute the app is live at **https://drewwhittick-creator.github.io/ProTrak/**

On a phone, open that address and use **Add to Home Screen** to get an app-like icon.

## Where data is stored

ProTrak syncs through **Firebase** (Google sign-in + Firestore):

- Sign in with Google and your projects follow you to any device where you sign in with the same account.
- It works offline and syncs when you reconnect.
- Each person's projects are stored under `users/<their id>/projects`, and the rules in `firestore.rules` let people read and write only their own data.
- Choosing **Use on this device only** skips sign-in and keeps projects in this browser's local storage. If you sign in later, the app offers to move those projects into your account.

### Firebase setup checklist

1. **Authentication → Sign-in method**: Google enabled.
2. **Authentication → Settings → Authorized domains**: `drewwhittick-creator.github.io` added.
3. **Firestore Database** created (Standard edition, production mode).
4. **Firestore Database → Rules**: replace the contents with `firestore.rules` and click **Publish**.

The `firebaseConfig` values in `index.html` identify the project and are safe to keep in a public repository. The security rules are what protect the data.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app: markup, styles and script |
| `firestore.rules` | Firestore security rules to paste into the Firebase console |
| `icon.svg`, `apple-touch-icon.png`, `icon-192.png`, `icon-512.png`, `favicon-32.png` | App icon for the home screen and browser tab |
| `manifest.webmanifest` | Lets Android and desktop browsers install ProTrak as an app |
| `README.md` | This file |

## Note on the repository

If the repository is public, anyone can see the code, but not your projects. Those are protected by your Google sign-in and the Firestore rules.
