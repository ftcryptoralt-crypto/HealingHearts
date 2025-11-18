# 🌐 Connect Your GoDaddy Domain to Render

This guide shows you exactly how to connect your GoDaddy domain to your HealingHearts app on Render.

---

## 📋 What You'll Need

- ✅ A domain from GoDaddy (e.g., `healinghearts.com`)
- ✅ Your app deployed on Render
- ✅ Access to GoDaddy DNS settings

---

## 🎯 Step-by-Step Instructions

### Step 1: Get Your Render DNS Information

1. Log in to **Render.com**
2. Click on your **HealingHearts** service
3. Go to **"Settings"** tab
4. Scroll down to **"Custom Domain"** section
5. Click **"+ Add Custom Domain"**
6. Enter your domain:
   - For root: `healinghearts.com`
   - For www: `www.healinghearts.com`
   - **Tip:** Add both!

7. Render will show you DNS records. **Keep this page open!**

---

### Step 2: Configure GoDaddy DNS

1. Log in to **GoDaddy.com**
2. Click **"My Products"**
3. Find your domain and click **"DNS"** button
4. This opens the DNS Management page

---

### Step 3A: Add Root Domain (healinghearts.com)

**In GoDaddy DNS Management:**

1. Look for existing **A** records with name `@`
2. Delete or edit the existing one
3. Add/Edit record:
   ```
   Type: A
   Name: @
   Value: [Copy the IP address from Render]
   TTL: 600 seconds (or 1 hour)
   ```
4. Click **"Save"**

---

### Step 3B: Add WWW Subdomain (www.healinghearts.com)

**In GoDaddy DNS Management:**

1. Look for existing **CNAME** records with name `www`
2. Delete the "Parked" CNAME if it exists
3. Click **"Add"** → Select **"CNAME"**
4. Fill in:
   ```
   Type: CNAME
   Name: www
   Value: healinghearts.onrender.com
   TTL: 600 seconds (or 1 hour)
   ```
5. Click **"Save"**

---

### Step 4: Wait for DNS Propagation

⏰ **DNS changes take time:**
- Minimum: 10-15 minutes
- Average: 30-60 minutes  
- Maximum: 24 hours (rare)

**Check if it's working:**
- Open a new browser (incognito/private mode)
- Visit: `http://yourdomain.com`
- If you see a "Not Secure" warning, wait a bit longer
- Once working, Render auto-generates SSL certificate (5-10 min)

---

## 🔐 SSL Certificate (HTTPS)

Render automatically provides **FREE SSL certificate** for your custom domain!

**After DNS propagates:**
1. Wait 5-10 minutes
2. Render automatically issues SSL
3. Your site becomes: `https://healinghearts.com` ✅

**Force HTTPS:**
In Render dashboard, under Custom Domain settings, enable:
- ✅ "Redirect HTTP to HTTPS"

---

## 📱 Example DNS Setup

### Example 1: Root Domain Only

**GoDaddy DNS Records:**
```
Type    Name    Value                      TTL
A       @       216.24.57.1                600
```

**Access your site:**
- ✅ `healinghearts.com`
- ✅ `https://healinghearts.com` (after SSL)

---

### Example 2: Both Root and WWW (Recommended)

**GoDaddy DNS Records:**
```
Type     Name    Value                        TTL
A        @       216.24.57.1                  600
CNAME    www     healinghearts.onrender.com   600
```

**Access your site:**
- ✅ `healinghearts.com`
- ✅ `www.healinghearts.com`
- ✅ Both redirect to HTTPS automatically

---

## 🐛 Troubleshooting

### "This site can't be reached"
**Cause:** DNS not propagated yet  
**Solution:** Wait 30-60 minutes, then try again

### "Not Secure" warning
**Cause:** SSL certificate not issued yet  
**Solution:** Wait 5-10 minutes after DNS works

### "DNS_PROBE_FINISHED_NXDOMAIN"
**Cause:** DNS records incorrect  
**Solution:** 
1. Double-check spelling in GoDaddy
2. Verify you used correct IP from Render
3. Make sure TTL is 600 or 3600

### Old website still showing
**Cause:** Browser cache or DNS cache  
**Solution:**
1. Clear browser cache (Ctrl+Shift+Delete)
2. Try incognito/private window
3. Flush DNS cache:
   - **Windows:** `ipconfig /flushdns`
   - **Mac:** `sudo dscacheutil -flushcache`
   - **Linux:** `sudo systemd-resolve --flush-caches`

### Still not working after 24 hours?
1. Verify DNS records in GoDaddy match Render exactly
2. Check Render dashboard for custom domain status
3. Contact Render support (they're very helpful!)

---

## 🎨 Advanced: Email Forwarding

**Want to use email@yourdomain.com?**

GoDaddy offers free email forwarding!

1. In GoDaddy, go to your domain
2. Click **"Email"** → **"Manage"**
3. Set up forwarding:
   ```
   contact@healinghearts.com → your-real-email@gmail.com
   support@healinghearts.com → your-real-email@gmail.com
   ```

4. Add MX records (GoDaddy does this automatically)

---

## 📊 Verify Your Setup

**Online DNS Checker Tools:**
- https://www.whatsmydns.net
- https://dnschecker.org

**Enter your domain and check:**
1. **A Record** for `@` → Should show Render IP
2. **CNAME Record** for `www` → Should show `healinghearts.onrender.com`

---

## ✅ Final Checklist

Before you're done, verify:

- [ ] Added A record for root domain (@)
- [ ] Added CNAME record for www subdomain
- [ ] Waited 30-60 minutes for DNS propagation
- [ ] Site loads at your custom domain
- [ ] SSL certificate issued (HTTPS works)
- [ ] Redirect from HTTP to HTTPS enabled
- [ ] Both www and non-www versions work

---

## 🎉 Success!

Your HealingHearts platform is now live at:
- ✅ `https://healinghearts.com` (or your domain)
- ✅ Professional custom domain
- ✅ Free SSL certificate
- ✅ Fully hosted and working!

**Share your site:**
```
🌟 HealingHearts - Mental Health Support Platform
🌐 https://healinghearts.com
💙 A safe space for emotional wellbeing
```

---

## 💡 Pro Tips

1. **Set up WWW redirect:**
   - Most people prefer `healinghearts.com` over `www.healinghearts.com`
   - Both will work, but one should redirect to the other
   - Render handles this automatically!

2. **Monitor uptime:**
   - Use free service like UptimeRobot.com
   - Pings your site every 5 minutes
   - Prevents Render free tier from sleeping
   - Sends alerts if site goes down

3. **Social media links:**
   - Update all social media profiles with new domain
   - Add to email signatures
   - Share on mental health communities

---

## 📞 Need Help?

- **GoDaddy DNS Support:** https://www.godaddy.com/help/dns-management-19192
- **Render Custom Domains:** https://render.com/docs/custom-domains
- **Community Help:** https://community.render.com

Good luck! Your platform will help so many people! 💙
