# Crystal Ville OAuth Setup

Production website:
https://playcrystalville.dpdns.org

## 1. Supabase

Authentication -> URL Configuration:

Site URL:
https://playcrystalville.dpdns.org

Redirect URL:
https://playcrystalville.dpdns.org/auth.html

## 2. Enable Discord

Supabase -> Authentication -> Sign In / Providers -> Discord.

Enter the Discord OAuth Client ID and Client Secret from your Discord Developer Portal application.

## 3. Discord Developer Portal

Discord Developer Portal -> Your Application -> OAuth2 -> Redirects:

https://sulaflsevtrsnztchsbm.supabase.co/auth/v1/callback

Do NOT put the Discord Client Secret in any website file.

## 4. Deploy

Upload all files in this ZIP to the Cloudflare-hosted website. Keep auth.html at the site root so this exact URL works:
https://playcrystalville.dpdns.org/auth.html

The included auth.html uses Supabase PKCE OAuth and redirects successful sessions to:
https://playcrystalville.dpdns.org/index.html#playerhub
