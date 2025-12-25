# CHABABE LAMTA Website Deployment Guide

## Quick Start - Deploy in 5 Minutes

Your website is production-ready and can be deployed to any of these platforms:

---

## Option 1: Vercel (Recommended - Easiest)

### Method A: GitHub Integration (Automatic)
1. Push your code to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Click "Import Project"
4. Select your GitHub repository
5. Vercel auto-detects Vite settings
6. Add environment variables:
   ```
   VITE_SUPABASE_URL=your_supabase_url
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```
7. Click "Deploy"
8. Your site is live! Vercel provides a free `.vercel.app` domain

### Method B: CLI Deployment
```bash
npm install -g vercel
vercel login
vercel
# Follow prompts, add environment variables when asked
```

**Custom Domain**: In Vercel dashboard → Settings → Domains → Add your domain

---

## Option 2: Netlify (Drag & Drop)

### Method A: Drag & Drop
1. Go to [netlify.com](https://netlify.com)
2. Sign up/login
3. Drag the `dist` folder directly onto Netlify dashboard
4. Site is live instantly!
5. Go to Site Settings → Environment Variables → Add:
   ```
   VITE_SUPABASE_URL=your_supabase_url
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```
6. Redeploy

### Method B: CLI Deployment
```bash
npm install -g netlify-cli
netlify login
netlify deploy --prod --dir=dist
```

**Custom Domain**: Site Settings → Domain Management → Add custom domain

---

## Option 3: Cloudflare Pages

1. Go to [dash.cloudflare.com](https://dash.cloudflare.com)
2. Pages → Create a project → Connect to Git
3. Select your repository
4. Build settings:
   - Framework preset: Vite
   - Build command: `npm run build`
   - Build output directory: `dist`
5. Add environment variables
6. Deploy

**Custom Domain**: Cloudflare Pages → Custom Domains → Add domain

---

## Environment Variables Required

All platforms need these environment variables:

```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key-here
```

Get these from your Supabase dashboard: Project Settings → API

---

## Custom Domain Setup (Any Platform)

### If you own a domain:

1. **At your domain registrar** (GoDaddy, Namecheap, etc.):
   - Add A record pointing to platform's IP, OR
   - Add CNAME record pointing to your deployment URL

2. **At your hosting platform**:
   - Add custom domain in settings
   - Wait for DNS propagation (5 mins - 24 hours)

### Example DNS Settings for Vercel:
```
Type: CNAME
Name: www
Value: cname.vercel-dns.com
```

### Don't have a domain yet?

Register one at:
- [Namecheap](https://namecheap.com) - ~$10/year
- [Google Domains](https://domains.google) - ~$12/year
- [Cloudflare Registrar](https://cloudflare.com) - At-cost pricing

Popular domain ideas:
- `chababelamta.com`
- `chababelamta.ma` (Moroccan domain)
- `lamtaoliveoil.com`
- `chababe.ma`

---

## Manual Deployment (Any Host)

If using traditional hosting (cPanel, shared hosting):

1. Build the project: `npm run build`
2. Upload entire `dist` folder contents via FTP
3. Point domain to this directory
4. Set environment variables in host control panel

---

## Post-Deployment Checklist

- [ ] Test all pages load correctly
- [ ] Verify language switcher works
- [ ] Test admin login: mohammedsahibchababe.lamta@gmail.com
- [ ] Check contact form submissions save to database
- [ ] Verify countdown timers work
- [ ] Test responsive design on mobile
- [ ] Check Supabase RLS policies are active
- [ ] Test member gating on Partners page
- [ ] Verify all images load

---

## SSL/HTTPS

All recommended platforms (Vercel, Netlify, Cloudflare) provide **free automatic SSL certificates**. Your site will be secure (https://) immediately.

---

## Need Help?

1. Check platform documentation
2. Verify Supabase credentials are correct
3. Check browser console for errors
4. Ensure environment variables are set correctly

---

## Current Build Stats

- Total size: 146 KB (gzipped: 47.71 KB)
- Lighthouse ready
- Fully optimized for production
- All 9 pages + admin area included

Your website is ready to go live! 🚀
