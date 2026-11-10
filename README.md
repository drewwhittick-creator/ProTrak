# Project Focus

A small, iPhone-style planner for prioritizing work projects. It ranks each project by **impact × urgency**, keeps a checklist of next steps, and shows how you're progressing over time.

It's a single HTML file with no build step, no dependencies and no server.

## Features

- **Focus list**: active projects ranked by impact × urgency, each showing its next step, which you can tick off right from the list.
- **Matrix view**: projects sorted into Do Now, Schedule, Quick Win and Later.
- **Automatic urgency**: urgency goes up as a due date gets close.
- **New-project quiz**: one question per screen (name, stakeholder, due date, impact, urgency, status, next steps), ending with a review screen.
- **Time tracking**: a "Spent Time on This Today" button in each project. Ticking off a step also counts. Cards show when you last worked on a project and flag ones untouched for 7+ days, and the All tab has a Neglected filter.
- **Project details**: next steps, stakeholder, due date, status and blockers, file location (with Open Link or Copy Location), and dated notes.
- **Completed Projects screen**: completion counts, average time to finish, on-time rate, steps per week, progress on open projects, weekly charts, and a button to clear completed projects.
- Light and dark mode, smooth transitions, and layouts that work on a phone and a laptop.

## Running it

Open `index.html` in any modern browser. Nothing else is needed.

### Hosting on GitHub Pages

1. Create a new repository and upload `index.html` and `README.md` to the root.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then **Save**.
4. After a minute the app is live at `https://<your-username>.github.io/<repo-name>/`.

On a phone, open that address and use **Add to Home Screen** to get an app-like icon.

## Where data is stored

This version saves projects in the browser's **local storage**:

- Data stays on the device and browser where you entered it. A laptop and a phone keep **separate** lists.
- Clearing browser data, or using a private window, removes it.
- Nothing is sent to GitHub or any server.

The original version runs as a Claude artifact, which syncs between devices through Claude's built-in storage. That storage only exists inside Claude, so this file falls back to local storage everywhere else. To get cross-device sync on GitHub Pages, you'd need to connect a backend such as Firebase or Supabase.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app: markup, styles and script |
| `README.md` | This file |

## Note on the repository

If the repository is public, anyone can see the code, but not your projects. Those stay in your own browser.
