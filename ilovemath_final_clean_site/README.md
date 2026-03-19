# I Love Math Admin Starter Pack

This starter pack adds a Decap CMS admin panel at `/admin` so you can create, edit, upload, and delete worksheets and videos without manually changing files in Netlify.

## What this gives you
- Admin login at `/admin`
- Worksheet collection
- Video collection
- Editable homepage and site settings
- PDF/image uploads to `assets/uploads`

## Put these files into your website repo
- `admin/index.html`
- `admin/config.yml`
- `netlify.toml`
- `content/...`
- `assets/js/netlify-identity-redirect.js`

## Netlify setup
1. In Netlify, open your site dashboard.
2. Enable **Identity**.
3. Set registration to **Invite only**.
4. Invite your own email as an admin/editor.
5. If your site uses Git Gateway with Decap, enable the matching gateway option required by your project configuration.

## Add Identity redirect script to your main homepage
Add these two snippets to your main site HTML:

### Inside `<head>`
```html
<script src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
```

### Before `</body>`
```html
<script src="/assets/js/netlify-identity-redirect.js"></script>
```

## Important
Your current homepage appears to have lesson cards hardcoded. To make uploads/deletes appear automatically, the lesson list must be changed to read from content files or a generated content source. This pack sets up the admin side first.

## Next coding step
Refactor the worksheet/video section so it renders from the files in `content/worksheets` and `content/videos` instead of hardcoded HTML.
