# Amex tracker

Upload your Amex CSV each month, keep a saved history, and see month-by-month analysis. Static site (one `index.html`) on GitHub Pages, with Supabase for login and storage.

## One-time setup

1. **Database.** Supabase dashboard > SQL Editor > New query. Paste all of `schema.sql` and click Run. Then do the same with `schema-budgets.sql` (budget groups).
2. **Site URL.** Supabase > Authentication > URL Configuration. Set Site URL to your GitHub Pages address (`https://YOUR-USERNAME.github.io/YOUR-REPO/`).
3. **Publish.** In your GitHub repo, Add file > Upload files, drop in `index.html`, commit. Then Settings > Pages > Source: Deploy from a branch > `main` / root > Save. Your address appears after a minute or so.
   - GitHub Pages on a free account only works for **public** repos. That is safe here: the only key in the code is the public one, and the database rules stop anyone reading your data without logging in. Otherwise upgrade, or host on Cloudflare Pages / Netlify instead.
4. **Create your account.** Open the site, enter your email and a password of 12+ characters, click Create account, confirm the email if asked, then sign in.
5. **Close sign-ups.** Supabase > Authentication > Sign In / Providers > turn off "Allow new users to sign up". Only your account can log in.

## Every month

Sign in, drop in the new CSV, check the preview (tick the flip box if charges show as negative), and press **Save to my history**. Anything already saved is skipped, so overlapping downloads are safe.

## Notes

- Never put the secret/service_role key or your database password in this repo.
- Category changes you make in the table are saved and applied to future uploads.
- To remove data: Supabase > Table Editor.
