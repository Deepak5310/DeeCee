# Domain Setup - www.deeceehairs.com

## ✅ Domain Configured

**Primary Domain:** https://www.deeceehairs.com

All SEO configurations have been updated to use the custom domain.

## 🔧 Vercel Domain Setup

### Step 1: Add Custom Domain
1. Go to [Vercel Dashboard](https://vercel.com/dashboard)
2. Select your project: **DeeCee2**
3. Go to **Settings** → **Domains**
4. Click **Add Domain**
5. Enter: `www.deeceehairs.com`
6. Click **Add**

### Step 2: Configure DNS Records

Add these DNS records in your domain registrar (where you bought deeceehairs.com):

#### Option A: Using www (Recommended)
```
Type: CNAME
Name: www
Value: cname.vercel-dns.com
```

#### Option B: Apex Domain (optional)
```
Type: A
Name: @
Value: 76.76.21.21

Type: CNAME
Name: www
Value: cname.vercel-dns.com
```

#### Option C: Redirect apex to www
```
Type: A
Name: @
Value: 76.76.21.21

(Vercel will auto-redirect deeceehairs.com → www.deeceehairs.com)
```

### Step 3: Wait for Verification
- DNS propagation: 24-48 hours (usually faster)
- Vercel will auto-detect DNS changes
- SSL certificate auto-issued by Vercel

### Step 4: Set as Primary Domain
1. In Vercel → Domains
2. Click ⋮ menu next to `www.deeceehairs.com`
3. Select **Set as Primary Domain**

## 📋 Post-Setup Checklist

### Immediate:
- [ ] Domain added in Vercel
- [ ] DNS records configured
- [ ] SSL certificate issued (auto)
- [ ] Domain set as primary

### After DNS Propagation:
- [ ] Test: https://www.deeceehairs.com (should load site)
- [ ] Test: https://deeceehairs.com (should redirect to www)
- [ ] Check SSL (green padlock in browser)
- [ ] Submit to Google Search Console

### SEO Setup:
- [ ] Google Search Console verification
- [ ] Submit sitemap: https://www.deeceehairs.com/sitemap.xml
- [ ] Google Analytics setup
- [ ] Bing Webmaster Tools

## 🌐 Domain Registrar DNS Settings

### Example: GoDaddy
```
1. Login to GoDaddy
2. My Products → DNS
3. Add Record:
   - Type: CNAME
   - Name: www
   - Value: cname.vercel-dns.com
   - TTL: 1 Hour
4. Save
```

### Example: Namecheap
```
1. Login to Namecheap
2. Domain List → Manage
3. Advanced DNS
4. Add New Record:
   - Type: CNAME Record
   - Host: www
   - Value: cname.vercel-dns.com
   - TTL: Automatic
5. Save
```

### Example: Cloudflare
```
1. Login to Cloudflare
2. Select domain
3. DNS → Records
4. Add record:
   - Type: CNAME
   - Name: www
   - Target: cname.vercel-dns.com
   - Proxy status: DNS only (gray cloud)
5. Save
```

## 🔍 Verify DNS Configuration

### Check DNS Propagation:
```bash
# Online tools:
https://dnschecker.org/#CNAME/www.deeceehairs.com
https://www.whatsmydns.net/#CNAME/www.deeceehairs.com

# Command line:
dig www.deeceehairs.com
nslookup www.deeceehairs.com
```

### Expected Result:
```
www.deeceehairs.com → CNAME → cname.vercel-dns.com
```

## 🚀 Environment Variables (if needed)

If your app needs the domain in environment variables:

```env
# .env.local or Vercel Environment Variables
NEXT_PUBLIC_SITE_URL=https://www.deeceehairs.com
NEXT_PUBLIC_API_URL=https://www.deeceehairs.com/api
```

Update in Vercel:
1. Settings → Environment Variables
2. Add `NEXT_PUBLIC_SITE_URL`
3. Value: `https://www.deeceehairs.com`
4. Environment: All (Production, Preview, Development)
5. Save → Redeploy

## 📧 Email Setup (Optional)

### Professional Email: contact@deeceehairs.com

**Option 1: Google Workspace**
- $6/user/month
- Gmail interface
- 30GB storage

**Option 2: Zoho Mail**
- Free for 1 domain, 5 users
- 5GB storage per user

**Option 3: Cloudflare Email Routing (Free)**
- Forward emails only
- contact@deeceehairs.com → your-gmail@gmail.com

### DNS Records for Email (Example: Google Workspace):
```
Type: MX
Priority: 1
Value: ASPMX.L.GOOGLE.COM

Type: MX
Priority: 5
Value: ALT1.ASPMX.L.GOOGLE.COM
```

## 🎯 SEO URLs Updated

All SEO configurations now use: **https://www.deeceehairs.com**

### Updated Files:
- ✅ `app/layout.tsx` - Metadata & structured data
- ✅ `app/sitemap.ts` - Sitemap generation
- ✅ `app/robots.ts` - Robots.txt
- ✅ `SEO_OPTIMIZATION.md` - Documentation

### URLs:
- **Homepage:** https://www.deeceehairs.com
- **Shop:** https://www.deeceehairs.com/shop
- **Sitemap:** https://www.deeceehairs.com/sitemap.xml
- **Robots:** https://www.deeceehairs.com/robots.txt
- **Manifest:** https://www.deeceehairs.com/manifest.json

## 🔐 SSL Certificate

**Automatic by Vercel:**
- Free SSL certificate (Let's Encrypt)
- Auto-renewal
- HTTPS enforced
- A+ rating on SSL Labs

**Test SSL:**
- https://www.ssllabs.com/ssltest/analyze.html?d=www.deeceehairs.com

## 📊 Analytics Setup

### Google Analytics:
```javascript
// Add to app/layout.tsx <head>
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX', {
    page_path: window.location.pathname,
  });
</script>
```

### Google Search Console:
1. Add property: https://www.deeceehairs.com
2. Verification methods:
   - HTML meta tag (in layout.tsx)
   - HTML file upload
   - DNS TXT record
   - Google Analytics

## ✅ Pre-Launch Checklist

Before announcing domain:
- [ ] Domain resolves correctly
- [ ] SSL certificate active (https works)
- [ ] All pages load without errors
- [ ] Forms work (contact, appointment)
- [ ] Firebase authentication works
- [ ] Email notifications work (SendGrid)
- [ ] Mobile responsive
- [ ] Cross-browser tested
- [ ] Google Search Console verified
- [ ] Sitemap submitted
- [ ] Analytics tracking

## 🐛 Troubleshooting

### Domain not resolving:
- Wait 24-48 hours for DNS propagation
- Clear DNS cache: `ipconfig /flushdns` (Windows) or `sudo dscacheutil -flushcache` (Mac)
- Check DNS records in registrar

### SSL not working:
- Wait for Vercel to issue certificate (5-10 minutes)
- Check domain is verified in Vercel
- Ensure DNS points to Vercel correctly

### Redirect loops:
- Disable CloudFlare proxy (gray cloud)
- Check Vercel redirect settings
- Clear browser cache

---

**Domain:** www.deeceehairs.com
**Status:** Configured & Ready
**Last Updated:** October 16, 2025
