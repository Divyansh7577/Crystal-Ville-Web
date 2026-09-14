# Crystal Ville Web 3.1 — Auth Hub

## What changed
- Proper player email/password login using Supabase Auth.
- Player dashboard is account-based instead of username-search based.
- Minecraft account linking with a 6-digit verification code.
- Admin Panel now has **Player Accounts & Minecraft Linking**.
- Admin can verify a pending Minecraft link; verification automatically attaches the matching player profile to that login.
- Existing Website Editor, Player Profiles, News/Events, Achievements and Link Manager remain.
- No web store or payment system.

## Important: Minecraft-side verification
The website can create and track the verification code, but it cannot prove that a person owns a Minecraft username by itself. Until Crystal Ville has a server-side verification plugin/API, an admin must confirm the player in-game and press **Verify** in Admin Panel.

For fully automatic verification later, install a small Paper plugin that reads the pending code and confirms it through a secure server-side endpoint.

## Supabase
The site uses the project's publishable frontend key. Never put a Supabase `service_role`/secret key in this repo.

If Supabase email confirmation is enabled, new players must confirm their email before their first login.


### Minecraft linking
1. Player creates/logs into a Player Hub account.
2. Player enters their Minecraft username and generates a 6-digit code.
3. In Minecraft, run `/cvlink <code>`.
4. CrystalCore calls the Supabase linking endpoint.
5. The account is marked verified and the Player Hub is linked to that Minecraft username.

CrystalCore must have the Supabase URL and publishable key in its `config.yml`. Never put a Supabase service-role/secret key in the plugin or website.
