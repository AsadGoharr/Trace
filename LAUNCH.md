# Trace — Launch Checklist

A step-by-step checklist to go from "almost ready" to public launch.

---

## Pre-Launch (Before Submitting to Chrome Web Store)

### Extension
- [ ] All platforms tested end-to-end (Google Docs, Slides, Notion, Overleaf, Word, Canvas)
- [ ] Human Engine fully tested — pauses feel natural, no robotic bursts
- [ ] Session persistence tested — close and reopen popup, trace resumes correctly
- [ ] Pro plan feature gating works (WPM cap, word limit, etc.)
- [ ] Extension icons (16, 48, 128px) finalized in `manifest.json`
- [ ] Manifest V3 permissions are minimal and justified
- [ ] `background.js` service worker has no console errors in production
- [ ] Tested on Chrome stable + Chrome Beta
- [ ] Extension popup is mobile-friendly (for users on small screens)

### Chrome Web Store Submission
- [ ] Developer account verified and $5 one-time fee paid
- [ ] Store listing copy written (title, short description, full description)
- [ ] Screenshots uploaded (1280×800 or 640×400, at least 1, max 5)
- [ ] Promotional tile image created (440×280)
- [ ] Privacy policy URL added (link to `/privacy` on site)
- [ ] Category set correctly (Productivity)
- [ ] Justified all permissions in the "Privacy practices" section
- [ ] Submitted for review (takes 1–3 business days)

---

## Website / Dashboard

- [ ] Live URL updated in showcase README and site footer
- [ ] Chrome Web Store link updated everywhere in `App.tsx` (all 3 `chromewebstore` href instances)
- [ ] Waitlist banner removed OR updated to "Now Live — Install Extension"
- [ ] Waitlist form CTA replaced with "Install Extension" button after launch
- [ ] Pricing page is accurate (free tier limits, Pro features)
- [ ] Stripe payments tested end-to-end in production (not test mode)
- [ ] Supabase RLS policies reviewed — no unauthorized data access possible
- [ ] All Supabase environment variables set in Vercel production
- [ ] 404 and error states look clean
- [ ] `robots.txt` / sitemap in place for SEO (optional but helpful)
- [ ] Vercel Analytics confirmed working

---

## Marketing — Launch Day

### Social
- [ ] Twitter/X post ready — short demo GIF + link to extension
- [ ] LinkedIn post ready (more formal, tag relevant communities)
- [ ] TikTok / YouTube Short recorded (screen recording of extension typing)

### Communities (post on launch day)
- [ ] Reddit: r/productivity
- [ ] Reddit: r/college
- [ ] Reddit: r/ChatGPT
- [ ] Reddit: r/GradSchool
- [ ] Reddit: r/writing
- [ ] Relevant university Discord servers / Facebook groups

### Product Hunt
- [ ] Product Hunt draft created at producthunt.com/posts/new
- [ ] Tagline written (60 chars max)
- [ ] First comment (maker's note) written explaining the story
- [ ] Launch scheduled or submitted for review
- [ ] Hunter confirmed (or self-hunting)
- [ ] Ask friends/users to upvote on launch day

### Email
- [ ] Waitlist email drafted — announce launch to everyone who signed up
- [ ] Email sent via Supabase Edge Function or email service (e.g. Resend, Brevo)

---

## Post-Launch (First Week)

- [ ] Monitor Chrome Web Store reviews — respond to every early review
- [ ] Watch Supabase logs for any auth or DB errors at scale
- [ ] Check Vercel Analytics for traffic spikes
- [ ] Follow up on Reddit/Twitter comments
- [ ] Fix any critical bugs within 24 hours
- [ ] Announce on Product Hunt "maker comment" once you have initial users

---

## Nice-to-Have (Later)

- [ ] Custom domain configured on Vercel (e.g. `usetrace.io`)
- [ ] Add affiliate / referral program
- [ ] Blog post: "How I built Trace" (drives SEO + developer interest)
- [ ] Add Firefox extension (Manifest V3 compatible)
- [ ] Public roadmap page on the site
