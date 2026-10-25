# GGL Notification & Circular Management System — Frontend prototype

## Files
- `index.html`: GitHub Pages login and authenticated dashboard shell.

## Publish on GitHub Pages
1. Create/open the intended GitHub repository.
2. Upload `index.html` to the repository root.
3. Open Settings → Pages.
4. Select the deployment branch and `/ (root)`, then save.
5. Open the published URL and test the sign-in page.

## Important security status
This is an integration prototype, not production-ready authentication. The Apps Script authentication code previously drafted needs a security review before real employee credentials are used. In particular, replace UUID-derived random values with a cryptographically secure random source, benchmark and verify PBKDF2, and add server-side rate limiting. Apps Script CacheService sessions can expire early. Do not put passwords, hashes, salts, or tokens into GitHub source code or logs.

The browser frontend calls the provided Apps Script `/exec` URL using `text/plain` to avoid a JSON content-type preflight. Browser cross-origin access can still fail depending on Apps Script redirects and response headers. Test from the deployed GitHub Pages origin. If it fails, use a supported backend/proxy or a different hosting design; do not disable browser security.
