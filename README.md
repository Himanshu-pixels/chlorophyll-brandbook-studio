# chlorophyll brandbook studio — team edition

A brand guidelines studio for the chlorophyll team: create, edit and publish brandbooks together.
Hosting: **Vercel** (from GitHub). Database, logins and file storage: **Supabase** (already set up).

## What's in this folder

| File | What it is |
|---|---|
| `index.html` | The whole app |
| `config.js` | Connects the app to the Supabase project (already filled in) |
| `vercel.json` | Small security headers for Vercel |
| `supabase/setup.sql` | The database setup, for reference (already applied) |

## Go live — step by step

### 1. Put the files on GitHub
1. github.com → **New repository** → name it `chlorophyll-brandbook-studio` → Private → **Create**.
2. Click **uploading an existing file** and drag in everything from this folder (keep the `supabase` folder as is).
3. **Commit changes**.

### 2. Deploy on Vercel
1. vercel.com → sign in with GitHub → **Add New → Project** → pick the repo → **Import**.
2. Framework Preset: **Other**. Leave Build Command empty. Output Directory: `./`.
3. **Deploy**. Copy your live address, e.g. `https://chlorophyll-brandbook-studio.vercel.app`.

### 3. Tell Supabase your address (required for sign-up emails and password resets)
1. Open https://supabase.com/dashboard/project/edrixkluesapamimzyst/auth/url-configuration
2. **Site URL**: paste your Vercel address.
3. **Redirect URLs** → **Add URL**: the same address, plus your custom domain later (e.g. `https://studio.chlorophyll.in`).
4. **Save**.

### 4. Create the admin account
1. Open your Vercel address → **Create account** with your **@chlorophyll.in** email.
2. Click the confirmation link in the email, then sign in.
3. The first account to join becomes **admin**.

### 5. Add your team
- Anyone with an **@chlorophyll.in** email can sign up and joins automatically as an editor.
- For other people (freelancers, clients): avatar menu → **Team & invites** → add their email, then send them the link. No email is sent automatically.
- Admins can make others admin, remove members, and change auto-join domains on the same page.

### 6. Custom domain (optional)
Vercel → Project → **Settings → Domains** → add e.g. `studio.chlorophyll.in` → create the DNS record Vercel shows at your domain provider. Then add that domain to Supabase **Redirect URLs** (step 3).

## Before real use
- **Email sending:** Supabase's built-in email is only for testing and sends just a few emails per hour. For a team, connect a mail service (Resend, Postmark, SendGrid…) under **Authentication → Emails → SMTP Settings**.
- **Free plan pausing:** free Supabase projects pause after about a week without activity. Upgrading to Pro keeps it always on and adds daily backups.

## How it works
- Everyone on the team sees and edits the same projects.
- Published brandbooks live at `https://<your-address>/#b-<name>` and open without an account. Password-protected ones are encrypted and need the password.
- Images and files are stored in the Supabase `brand-assets` bucket.

## Updating the app later
Upload a new `index.html` to the GitHub repo (same name) → Vercel redeploys automatically.
