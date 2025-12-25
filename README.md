# CHABABE LAMTA - Agricultural Cooperative & Olive Oil Brand Website

A fully responsive, multilingual, SEO-optimized website for CHABABE LAMTA agricultural cooperative in Morocco.

## Features

### Core Functionality
- **9 Public Pages**: Home, Cooperative, Location, Olive Oil, Heritage, Partners, Gift/Sponsorship, About, Contact
- **Admin Dashboard**: Full content management system for products, testimonials, offers, leads
- **Authentication**: Member accounts + admin/CEO roles
- **Multilingual**: EN, FR, DE, ES, IT, Darija (auto-detect browser language)
- **E-commerce Ready**: Product catalog, sponsorship tiers, newsletter capture

### Special Features
- **Dynamic Countdown Timers**: Limited-time offers with localStorage persistence
- **Gated Content**: Member-only access to partner project details
- **Lead Capture**: Multiple forms (contact, newsletter, diet requests)
- **Trust Badges**: TERROIR DU MAROC & ONSSA certification display
- **Responsive Design**: Mobile-first, tablet, desktop optimized
- **SEO Optimized**: Semantic HTML, meta tags, OpenGraph ready

### Admin Accounts
- **Admin**: mohammedsahibchababe.lamta@gmail.com / S+Lmh32QUEA3ts9
- **CEO**: aziz.sahib@chababe.lamta.ma / Rg_*Z3J!8:y-#:M

## Tech Stack

- **Frontend**: React 18 + TypeScript + Vite
- **Styling**: Tailwind CSS
- **Backend**: Supabase (PostgreSQL)
- **Auth**: Supabase Auth
- **Icons**: Lucide React
- **Routing**: React Router DOM

## Local Development

### 1. Install Dependencies
```bash
npm install
```

### 2. Configure Environment Variables
```bash
cp .env.example .env.local
```

Edit `.env.local` with your Supabase credentials:
```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key
```

### 3. Set Up Database
Run the migration SQL from `supabase/migrations/` in your Supabase SQL Editor:
- Creates all tables (products, testimonials, leads, etc.)
- Sets up Row-Level Security policies
- Seeds initial data

### 4. Start Development Server
```bash
npm run dev
```

Visit `http://localhost:5173`

### 5. Build for Production
```bash
npm run build
npm run preview
```

## Deployment

See **[DEPLOYMENT.md](./DEPLOYMENT.md)** for complete deployment instructions to:
- Vercel (recommended)
- Netlify
- Cloudflare Pages
- Any custom hosting

**Quick Deploy to Vercel:**
```bash
npm install -g vercel
vercel
```

## Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── Hero.tsx
│   ├── Header.tsx
│   ├── Footer.tsx
│   ├── ProductCard.tsx
│   ├── CountdownTimer.tsx
│   └── ...
├── pages/              # Page components
│   ├── Home.tsx
│   ├── Cooperative.tsx
│   ├── admin/
│   │   ├── AdminDashboard.tsx
│   │   ├── AdminProducts.tsx
│   │   └── ...
│   └── ...
├── contexts/           # React contexts
│   ├── AuthContext.tsx
│   └── LanguageContext.tsx
├── translations/       # i18n JSON files
│   ├── en.json
│   ├── fr.json
│   └── ...
├── lib/
│   └── supabase.ts    # Supabase client
└── App.tsx            # Main app with routing
```

## Database Schema

### Tables
- `products` - Olive oil products catalog
- `testimonials` - Customer reviews
- `leads` - Form submissions (contact, newsletter)
- `blog_posts` - Blog content
- `offers` - Dynamic promotional offers
- `tiers` - Sponsorship packages
- `media` - Image management
- `commendations` - User-submitted commendations
- `site_content` - CMS-editable page content
- `profiles` - User profiles (linked to auth.users)

## Key Pages

### Public Pages
- **/** - Home (hero, services, products, testimonials, newsletter)
- **/cooperative** - Team and mission
- **/location** - Address, map, directions
- **/olive-oil** - Product catalog
- **/heritage** - Olive variety storytelling
- **/partners** - GIE project details (gated)
- **/gift** - Sponsorship program
- **/about** - About the cooperative
- **/contact** - Contact form

### Admin Area
- **/admin** - Dashboard overview
- **/admin/products** - Manage products
- **/admin/testimonials** - Manage reviews
- **/admin/offers** - Dynamic offer management
- **/admin/leads** - View form submissions

## Admin Features

The admin can edit:
- ✅ Products (name, description, price, image, tasting notes)
- ✅ Testimonials (add, edit, delete customer reviews)
- ✅ Offers (countdown timers, discount text)
- ✅ Leads (view contact form submissions)
- ✅ Blog posts (create educational content)
- ⏳ Media library (upload/manage images)
- ⏳ Page content (edit hero text, sections)

## Languages Supported

- **English** (EN) - Default fallback
- **French** (FR)
- **German** (DE)
- **Spanish** (ES)
- **Italian** (IT)
- **Darija** (Moroccan Arabic)

Language auto-detected from browser, switchable via header menu.

## Performance

- **Bundle Size**: 146 KB (47 KB gzipped)
- **Lighthouse Ready**: Optimized images, lazy loading
- **Accessibility**: ARIA labels, keyboard navigation
- **SEO**: Semantic HTML, meta tags, OpenGraph

## Security

- Row-Level Security (RLS) enabled on all tables
- Admin-only routes protected
- HTTPS enforced (via hosting platform)
- Environment variables for sensitive data
- Password hashing via Supabase Auth

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

Proprietary - CHABABE LAMTA Agricultural Cooperative

## Support

For technical support:
- Admin: mohammedsahibchababe.lamta@gmail.com
- CEO: aziz.sahib@chababe.lamta.ma

---

Built with React + Supabase | Ready for Production 🚀
