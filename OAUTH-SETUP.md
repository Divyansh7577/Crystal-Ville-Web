# Crystal Ville Discord OAuth Setup

The website files/design are preserved. OAuth changes are limited to the authentication flow.

## Production website
https://playcrystalville.dpdns.org

## Supabase
Authentication -> URL Configuration:

Site URL:
https://playcrystalville.dpdns.org

Redirect URL:
https://playcrystalville.dpdns.org/auth.html

## Discord Developer Portal
OAuth2 -> Redirects:

https://sulaflsevtrsnztchsbm.supabase.co/auth/v1/callback

## Supabase Discord Provider
Authentication -> Sign In / Providers -> Discord:
- Enable Discord
- Enter the Discord Client ID
- Enter the Discord Client Secret

Do not put the Discord Client Secret in any HTML/JS file.

## What was changed
- auth.html: Discord OAuth now redirects to the real production auth.html URL and uses PKCE.
- index.html: the existing Discord button now starts the same OAuth flow and returns through auth.html.
- Existing website pages, styling, admin panel, links, dashboard, assets, and configuration were preserved.
