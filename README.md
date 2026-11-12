# Portfolio site — setup

## 1. Images
Already added and compressed in `images/` and `images/work/`.
To add more work samples: save the image into `images/work/`, then in index.html
copy one `<figure>` line in the right gallery and change the file name and caption.
Good extras to add later: LinkedIn cover, conference banner, logo, Trello / monday.com boards,
and a current ad creative (no client branding).

## 2. Fill in the placeholders (search index.html for these)
- Bookings use Calendly (link set in index.html, search `calendly.com`) — no form key needed
- `href="#"` → Telegram, LinkedIn, and the 3 video links
- `Results` block in the Paid Ads section → add real numbers you're allowed to share
- Commented "Copy this block for earlier roles" in Experience → add older jobs

## 3. Push with your PERSONAL accounts
```bash
cd portfolio
git init
git config user.name "Your Name"
git config user.email "your-personal@email.com"   # this repo only
git add . && git commit -m "Portfolio site"
git branch -M main
git remote add origin https://github.com/YOUR-PERSONAL-USERNAME/portfolio.git
git push -u origin main
```
If VS Code pushes as your client account, sign out under Accounts (bottom-left) first.

## 4. Deploy
In a separate browser profile, log in to Vercel with your personal GitHub →
Add New → Project → import `portfolio` → Deploy (no build settings needed).

## 5. Tracking
- **Vercel Analytics (visits):** Vercel → your project → Analytics → Enable. Nothing to paste.
- **Google Analytics 4 (visits + events):** create a GA4 property → Web data stream for your site URL →
  copy the Measurement ID (G-XXXXXXXXXX) → paste it into `GA_ID` near the bottom of index.html.
- Events sent: `book_call_click`, `calendly_time_selected`, `calendly_booked`, `contact_click`
  (whatsapp / telegram / linkedin / email), `portfolio_tab`, `video_click`, `feedback_pdf_view`.
- In GA4, mark `calendly_booked` as a Key event (Admin → Events).
- Add UTMs to links you share, e.g. `?utm_source=linkedin`, `?utm_source=application&utm_campaign=company-name`.
