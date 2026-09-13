# Crystal Ville Web 2.0 — Setup

This ZIP is a static website connected to the Crystal Ville Supabase project.

## 1. Upload the files
Upload the contents of this folder to your GitHub repository (or Netlify/Vercel/static hosting).

## 2. Supabase backend
The required tables/RLS are already configured in the Crystal Ville Supabase project:
- `site_settings`
- `website_links`
- `admin_users`

## 3. Create the first admin
Do NOT put an admin password in frontend code.

In Supabase Dashboard:
1. Open Authentication → Users.
2. Create/sign up the admin account using your own email/password.
3. Copy that user's UUID.
4. Open SQL Editor and run:

INSERT INTO public.admin_users (user_id)
VALUES ('PASTE_YOUR_AUTH_USER_UUID_HERE')
ON CONFLICT (user_id) DO NOTHING;

Then open `admin.html` and sign in.

## 4. What the Admin Panel can edit
- Site title
- Tagline
- Server IP
- Discord URL
- Link Tree links
- Link title / URL / icon / description
- Link enabled/disabled
- Add and delete links

The frontend uses only the Supabase publishable key. No service-role/secret key is included.


## Important: Website Editor sync
Version 2.1 fixes the homepage sync issue: Server IP and homepage settings saved from
`admin.html` are now loaded from Supabase when `index.html` opens. After committing
the updated files to GitHub/Netlify, open the site once with a fresh reload.
