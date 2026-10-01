# Paklance: complete website (frontend + backend)

Everything approved in the review build (Tasks 1–14), running on a real backend with a database.

## What's in this folder

| Folder / file | What it is |
|---|---|
| `paklance/` | **The app to run.** Frontend and backend together: the website is in `paklance/public/`, the backend (Node.js + Express API, database, emails, admin tools) is in `paklance/src/`. Full guide: `paklance/README.md`. |
| `preview/paklance-review-build.html` | The approved design as one file (same as the review link). Opens in any browser without a server, with sample data and a preview sign-up. |

## Run it (5 minutes)

1. Install **Node.js 22 or newer** from https://nodejs.org.
2. Open a terminal in the `paklance` folder and run:

   ```bash
   npm install
   cp .env.example .env        # Windows: copy .env.example .env
   npm start
   ```

3. Open **http://localhost:3000**.

The database (SQLite) and the sample content are created on the first start. Verification codes and other emails are printed in the terminal until an email server is set up.

Demo logins (local only): `demo@paklance.com` and `client@paklance.com`, password `Paklance123`.

## What the backend now covers

Everything from the earlier backend (sign-up and login, jobs, hiring, contracts, SafePay escrow, wallet, withdrawals, disputes, notifications, Match, Global Hiring, blog, newsletter, admin), plus the work finished since:

| Review build task | Backend |
|---|---|
| 4. Profile tracker, PKR price range | Profile sections saved per account; jobs filtered by budget range |
| 5. Profile page, video introduction, seminars, ratings | Public profile data; video link or file upload; seminar dates with registration and a confirmation email; after a finished contract the client and specialist review each other, and the stars and reviews appear on both profiles |
| 7. Profile photo | Photo upload (JPG, PNG, WebP), shown on the profile, header and specialist cards |
| 14. Blog engagement | Key takeaways, checklists and next-step buttons stored per article; "Was this helpful?" answers saved, with a report for the team |
| 6, 8–13 (homepage order, fonts, logo, motion, engaging pages, speed) | Frontend only, served as approved (the fee calculator uses the fees set on the server) |

## Checked

- 19 automated API tests pass on SQLite and PostgreSQL (`npm test`).
- A browser walkthrough of the running site passed: sign up, photo and video upload, seminars, blog feedback, reviewing a finished contract, ratings on profiles, and phone width, with no console or security errors.

## Before going live

See **section 2 of `paklance/README.md`**: PostgreSQL, HTTPS, email, Google sign-in, the escrow bank account, real fees, a persistent folder for uploads, real seminar dates, and the banking partner for payments. JazzCash and Easypaisa stay "coming soon" until merchant onboarding is complete.
