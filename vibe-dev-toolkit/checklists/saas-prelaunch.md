# SaaS Pre-Launch Checklist

Run through this list top to bottom before you go live. Don't skip anything.

---

## ⚖️ Legal & Compliance

- [ ] Privacy Policy page live
- [ ] Terms & Conditions (Terms of Service) live
- [ ] Cookie consent banner (especially if targeting EU — GDPR)

---

## 🔐 Auth & Security

- [ ] Signup / login flow tested end-to-end
- [ ] Email verification working
- [ ] Password reset flow tested
- [ ] OAuth (Google, GitHub, etc.) working if included
- [ ] Rate limiting active on auth endpoints (prevent brute force)

---

## 💳 Payments

- [ ] Payment flow fully tested — success AND failure cases
- [ ] Subscription lifecycle working:
  - [ ] Upgrade
  - [ ] Downgrade
  - [ ] Cancel
- [ ] Webhook handling for payment events

---

## 📊 Analytics & Tracking

- [ ] User event tracking set up (PostHog / Mixpanel / Amplitude)
- [ ] Page view tracking active
- [ ] Google Analytics connected

---

## 📣 SEO & Marketing

- [ ] Website submitted to Google Search Console
- [ ] sitemap.xml submitted
- [ ] Submitted to Bing Webmaster Tools
- [ ] PageSpeed score 70+ on mobile
- [ ] All SEO basics done (see guides/ai-website-seo-guide.pdf)

---

## 💬 Feedback Loop

- [ ] Contact / support email set up and working
- [ ] Bug report option visible to users
- [ ] Custom 404 page created
- [ ] Favicon added
- [ ] All broken links checked and fixed
