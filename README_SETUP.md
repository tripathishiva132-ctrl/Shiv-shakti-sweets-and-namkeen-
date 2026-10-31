# Shiv Shakti Sweets & Namkeen — GitHub + no-code admin

## What this package contains
- `index.html`: responsive storefront and admin dashboard
- `supabase_setup.sql`: database tables, starter catalogue and access policies

## Important hosting fact
GitHub Pages serves static files. It cannot securely store passwords, orders, product edits or uploaded images by itself. This package uses Supabase as the backend. The owner edits the site from the Admin page; no HTML/code editing is needed for everyday changes.

## One-time setup
1. Create a GitHub repository, for example `shiv-shakti-sweets`.
2. Upload `index.html` to the repository root.
3. In GitHub: Settings → Pages → Deploy from a branch → `main` → `/ (root)` → Save.
4. Create a Supabase project at https://supabase.com.
5. In Supabase → SQL Editor, paste and run all of `supabase_setup.sql`.
6. In that SQL, replace BOTH occurrences of `admin@example.com` with the exact email you will use for the single admin account. Run the SQL after replacing it.
7. Supabase → Authentication → Users → Add user. Create the one admin email and a strong password. Do not enable public sign-ups.
8. Supabase → Project Settings → API. Copy the Project URL and the `anon` / publishable public key (never the `service_role` secret).
9. Open your GitHub Pages website, go to Admin at the bottom of the page, then Website settings. Paste the Project URL and public anon key and save. The site reloads and connects.
10. Sign in on Admin using the admin email/password created in step 7.

## What the admin can change
- Add products, edit names/categories/prices, hide or delete products
- Change homepage headline, description and announcement strip
- Change shop name, address, WhatsApp number and opening hours
- View incoming enquiries and orders

## Notes / current limitations
- The displayed starter prices are examples. Verify and replace them before publishing.
- Product photos currently accept a public image URL; a managed image uploader / Storage bucket can be added after initial setup.
- Orders are sent to WhatsApp when a shop WhatsApp number is configured; the database also records them when connected.
- This is a starter deployment. Before taking online payments, integrate a payment provider and review privacy, tax and consumer rules.
- The public anon key is okay to place in the frontend only because the SQL policies restrict admin actions. Never paste a Supabase service-role key into the website.
- The admin email must match the address used in the SQL policies exactly.
