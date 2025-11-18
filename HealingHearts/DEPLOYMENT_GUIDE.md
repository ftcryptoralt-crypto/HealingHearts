# 🚀 HealingHearts Deployment Guide - Render.com (100% FREE)

This guide will help you deploy your HealingHearts mental health platform to Render.com completely free!

## 📋 Prerequisites

Before you begin, make sure you have:
- ✅ A GitHub account
- ✅ Your HealingHearts code pushed to GitHub repository
- ✅ A Render.com account (free - sign up at render.com)

---

## 🎯 Step 1: Push Your Code to GitHub

1. **Make sure your latest changes are committed:**
   ```bash
   git add .
   git commit -m "Ready for Render deployment"
   git push origin main
   ```

2. **Verify your GitHub repository:**
   - Go to: https://github.com/Pokemonexgxpo/Healinghearts
   - Make sure you see the latest code with the `render.yaml` file

---

## 🌐 Step 2: Deploy to Render.com

### A. Sign Up / Log In to Render

1. Go to **https://render.com**
2. Click **"Get Started for Free"**
3. Sign up using your **GitHub account** (recommended)
4. Authorize Render to access your GitHub repositories

### B. Create New Web Service

1. Click the **"New +"** button in the top right
2. Select **"Web Service"**
3. Click **"Connect a repository"**
4. Find and select: **Pokemonexgxpo/Healinghearts**
5. Click **"Connect"**

### C. Configure Your Service

Fill in the following settings:

**Basic Settings:**
- **Name:** `healinghearts` (or any name you prefer)
- **Region:** Choose closest to you (e.g., `Oregon (US West)`)
- **Branch:** `main`
- **Root Directory:** `HealingHearts`
- **Runtime:** `Node`

**Build & Deploy Settings:**
- **Build Command:** 
  ```
  npm install && npm run build
  ```

- **Start Command:**
  ```
  node server/production.js
  ```

**Plan:**
- Select **"Free"** plan (at the bottom)

**Environment Variables:**
Click **"Add Environment Variable"** and add:
- **Key:** `NODE_ENV`  
  **Value:** `production`

- **Key:** `ADMIN_PASSWORD`  
  **Value:** `admin123` (or your preferred admin password)

### D. Deploy!

1. Click **"Create Web Service"** at the bottom
2. Wait 5-10 minutes for the first deployment
3. Watch the deployment logs - you should see:
   ```
   ==> Building...
   ==> Deploying...
   ==> Your service is live!
   ```

---

## ✅ Step 3: Test Your Deployment

1. Once deployed, Render will give you a URL like:
   ```
   https://healinghearts.onrender.com
   ```

2. **Click the URL** to test your site

3. **Verify all features work:**
   - ✅ FAQ section loads
   - ✅ Blog posts visible
   - ✅ Games (Spinning Wheel & Cup Game) work
   - ✅ Quiz system functions
   - ✅ Quotes display
   - ✅ Chat connects (may take 30 seconds on first load)
   - ✅ Admin login works

---

## 🔧 Step 4: Set Admin Password

Your admin password is set via the `ADMIN_PASSWORD` environment variable.

**To change it:**
1. In Render dashboard, go to your service
2. Click **"Environment"** tab
3. Find `ADMIN_PASSWORD`
4. Click **"Edit"** → Change value → **"Save Changes"**
5. Service will automatically redeploy

---

## 🌍 Step 5: Connect Your GoDaddy Domain (Optional)

### A. In Render Dashboard:

1. Go to your service in Render
2. Click **"Settings"** tab
3. Scroll to **"Custom Domain"**
4. Click **"Add Custom Domain"**
5. Enter your domain (e.g., `healinghearts.com` or `www.healinghearts.com`)
6. Render will show you DNS records to add

### B. In GoDaddy:

1. Log in to **GoDaddy.com**
2. Go to **"My Products"** → **"DNS"** for your domain
3. Click **"Manage DNS"**

**If using root domain (healinghearts.com):**
- Type: `A`
- Name: `@`
- Value: `[IP address from Render]`
- TTL: `600 seconds`

**If using www (www.healinghearts.com):**
- Type: `CNAME`
- Name: `www`
- Value: `healinghearts.onrender.com`
- TTL: `600 seconds`

4. Click **"Save"**
5. Wait 10-60 minutes for DNS propagation
6. Visit your custom domain!

---

## ⚠️ Important Notes About Free Tier

### Sleep Mode:
- Your app **sleeps after 15 minutes** of no visitors
- First visitor after sleep will wait **~30 seconds** for wake-up
- After wake-up, app works at full speed

### How to minimize sleep impact:
- Use a free uptime monitor (like **UptimeRobot.com**) to ping your site every 5 minutes
- This keeps your app awake during peak hours

---

## 🔄 Automatic Updates

Every time you push to GitHub, Render automatically:
1. Detects the changes
2. Rebuilds your app
3. Deploys the new version
4. Zero downtime!

**To deploy updates:**
```bash
git add .
git commit -m "Update feature X"
git push origin main
```

That's it! Render does the rest.

---

## 🐛 Troubleshooting

### App won't start:
- Check **Logs** tab in Render dashboard
- Look for errors in build or deployment
- Verify environment variables are set correctly

### Chat not working:
- Wait 30 seconds after first load (wake-up time)
- Check browser console for WebSocket errors
- Verify WebSocket is enabled in Render (it is by default)

### Can't access admin:
- Verify `ADMIN_PASSWORD` environment variable is set
- Try clearing browser cache
- Check you're using the correct password

### Domain not working:
- Wait up to 1 hour for DNS propagation
- Verify DNS records are correct in GoDaddy
- Try clearing DNS cache: `ipconfig /flushdns` (Windows) or `sudo dscacheutil -flushcache` (Mac)

---

## 📊 Monitoring Your App

**View Logs:**
- Render Dashboard → Your Service → **"Logs"** tab

**View Metrics:**
- Render Dashboard → Your Service → **"Metrics"** tab
- See CPU, Memory, Request counts

**View Events:**
- Render Dashboard → Your Service → **"Events"** tab
- See all deployments and service changes

---

## 💰 Render Free Tier Limits

✅ **What's included for FREE:**
- 750 hours/month (enough for 24/7 uptime)
- 512MB RAM
- Unlimited bandwidth
- Free SSL certificate
- Custom domain support
- WebSocket support
- Automatic deploys from GitHub

⚠️ **Limitations:**
- App sleeps after 15 min inactivity
- Limited to 0.1 CPU
- Shared infrastructure

---

## 🎉 You're Done!

Your HealingHearts mental health platform is now live and accessible to anyone in the world - completely free!

**Your live URL:** https://healinghearts.onrender.com

**Share it with:**
- Friends who might need support
- Mental health communities
- Social media
- Your school/workplace

Remember: This platform provides valuable mental health resources. Keep it updated and monitor it regularly!

---

## 📞 Need Help?

- **Render Docs:** https://render.com/docs
- **Render Community:** https://community.render.com
- **GitHub Issues:** https://github.com/Pokemonexgxpo/Healinghearts/issues

Good luck! 🌟
