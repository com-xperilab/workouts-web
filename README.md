# workouts.xperilab.com

Public web host for Elite Workouts. Serves two things the app depends on:

- `.well-known/apple-app-site-association` — tells iOS which app owns `/w/*`
  links. Must be served over HTTPS with no redirect; Apple's CDN will not follow one.
- `w/index.html` — the fallback page a shared workout link opens when the app
  is not installed. The workout itself lives in the URL fragment (`#…`), which
  browsers never send to the server.

`.nojekyll` is required: without it GitHub Pages hides `.well-known/` and
universal links 404.

**Source of truth is the `web/` directory in the private `workouts` app repo.**
Edit there, then copy here (or let the sync action do it once it exists).
