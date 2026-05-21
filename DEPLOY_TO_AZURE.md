# 🚀 Deploy Dropa Landing Page to Azure (FREE)

**Quick guide to deploy your landing page to Azure Static Web Apps for free.**

---

## 🎯 Why Azure Static Web Apps?

- ✅ **100% FREE** - No credit card required
- ✅ **Custom domain** support
- ✅ **Free SSL** certificate
- ✅ **Global CDN** for fast loading
- ✅ **Easy deployment** - Drag & drop
- ✅ **99.95% uptime** SLA

---

## 🚀 Method 1: Azure Portal (Easiest - 5 Minutes)

### **Step 1: Create Azure Account**
1. Go to: https://azure.microsoft.com/free
2. Click "Start free"
3. Sign up with email (no credit card needed for free tier)

### **Step 2: Create Static Web App**
1. Login to: https://portal.azure.com
2. Search for "Static Web Apps" in the search bar
3. Click "Create"
4. Fill in details:
   ```
   Subscription: Free Trial (or your subscription)
   Resource Group: Click "Create new" → Name it "dropa-rg"
   Name: dropa-landing
   Plan type: Free
   Region: East US 2 (or closest to you)
   Deployment source: Other
   ```
5. Click "Review + create"
6. Click "Create"
7. Wait 1-2 minutes for deployment

### **Step 3: Upload Your Website**
1. After creation, click "Go to resource"
2. In the overview page, you'll see an "Upload" button
3. Click "Upload"
4. **Drag and drop ALL files** from the `landing-page` folder:
   - index.html
   - styles.css
   - script.js
   - staticwebapp.config.json
5. Click "Upload"
6. Wait 1-2 minutes

### **Step 4: Get Your Live URL**
1. In the overview page, find "URL"
2. Copy the URL (e.g., `https://nice-beach-123.azurestaticapps.net`)
3. Click the URL to view your live site!

---

## 🚀 Method 2: Azure CLI (For Developers)

### **Step 1: Install Azure CLI**
```bash
# Windows (PowerShell as Admin)
winget install Microsoft.AzureCLI

# Or download from:
# https://aka.ms/installazurecliwindows
```

### **Step 2: Login**
```bash
az login
# Browser opens, login with your Azure account
```

### **Step 3: Create Static Web App**
```bash
# Create resource group
az group create --name dropa-rg --location eastus2

# Create static web app
az staticwebapp create \
  --name dropa-landing \
  --resource-group dropa-rg \
  --location eastus2
```

### **Step 4: Deploy**
```bash
cd landing-page

# Deploy all files
az staticwebapp upload \
  --name dropa-landing \
  --resource-group dropa-rg \
  --source .
```

### **Step 5: Get URL**
```bash
az staticwebapp show \
  --name dropa-landing \
  --resource-group dropa-rg \
  --query "defaultHostname" \
  --output tsv
```

---

## 🚀 Method 3: GitHub Actions (Automated CI/CD)

### **Step 1: Push to GitHub**
```bash
cd landing-page
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin YOUR_GITHUB_REPO_URL
git push -u origin main
```

### **Step 2: Create Static Web App with GitHub**
1. Go to: https://portal.azure.com
2. Create Static Web App
3. Choose "GitHub" as deployment source
4. Authorize GitHub
5. Select your repository
6. Select branch: `main`
7. Build presets: "Custom"
8. App location: `/`
9. Click "Review + create"

### **Step 3: Automatic Deployment**
- Azure creates a GitHub Actions workflow
- Every push to `main` automatically deploys
- Check deployment status in GitHub Actions tab

---

## 🌐 Configure Custom Domain (Optional)

### **Step 1: Add Custom Domain**
1. In Azure Portal, go to your Static Web App
2. Click "Custom domains" in the left menu
3. Click "Add"
4. Enter your domain: `www.dropa.co.za`
5. Azure provides DNS records

### **Step 2: Update DNS**
1. Go to your domain registrar (e.g., GoDaddy, Namecheap)
2. Add the CNAME record provided by Azure:
   ```
   Type: CNAME
   Name: www
   Value: nice-beach-123.azurestaticapps.net
   TTL: 3600
   ```
3. Wait 5-60 minutes for DNS propagation

### **Step 3: Verify**
1. In Azure Portal, click "Validate"
2. Once verified, SSL certificate is automatically issued
3. Your site is now live at `https://www.dropa.co.za`

---

## ✅ Verify Deployment

### **Test Your Live Site:**
1. Visit your Azure URL
2. Check all sections load correctly
3. Test mobile responsiveness (resize browser)
4. Click all buttons and links
5. Test mobile menu
6. Check animations work

### **Performance Check:**
1. Go to: https://pagespeed.web.dev
2. Enter your Azure URL
3. Should score 90+ on performance

---

## 🔧 Update Your Site

### **Method 1: Re-upload via Portal**
1. Make changes to your files locally
2. Go to Azure Portal → Your Static Web App
3. Click "Upload"
4. Drag and drop updated files
5. Changes are live in 1-2 minutes

### **Method 2: Azure CLI**
```bash
cd landing-page
# Make your changes
az staticwebapp upload \
  --name dropa-landing \
  --resource-group dropa-rg \
  --source .
```

### **Method 3: Git Push (if using GitHub)**
```bash
git add .
git commit -m "Update landing page"
git push
# Automatically deploys in 2-3 minutes
```

---

## 📊 Monitor Your Site

### **View Analytics:**
1. Azure Portal → Your Static Web App
2. Click "Metrics" to see:
   - Page views
   - Bandwidth usage
   - Response times
   - Errors

### **Add Google Analytics:**
Edit `index.html`, add before `</head>`:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

---

## 🎉 Your Site is Live!

**What you have now:**
- ✅ Professional landing page
- ✅ Hosted on Azure (FREE)
- ✅ Global CDN for fast loading
- ✅ Free SSL certificate (HTTPS)
- ✅ 99.95% uptime guarantee
- ✅ Custom domain support

**Your URLs:**
```
Landing Page: https://dropa-landing.azurestaticapps.net
Customer App: https://dropa-customer.netlify.app
Driver App:   https://dropa-driver.netlify.app
Admin Panel:  https://dropa-admin.netlify.app
```

---

## 🐛 Troubleshooting

### **Site not loading:**
- Wait 2-3 minutes after upload
- Clear browser cache (Ctrl+Shift+R)
- Check Azure Portal for deployment status

### **Styles not working:**
- Ensure `styles.css` was uploaded
- Check browser console for errors
- Verify file names are correct (case-sensitive)

### **Links not working:**
- Update URLs in `index.html`
- Ensure target apps are deployed
- Test in incognito mode

### **Custom domain not working:**
- Wait up to 60 minutes for DNS propagation
- Verify CNAME record is correct
- Use https://dnschecker.org to check DNS

---

## 📞 Need Help?

**Azure Support:**
- Free tier includes community support
- Documentation: https://docs.microsoft.com/azure/static-web-apps

**Dropa Support:**
- Email: support@dropa.co.za
- Phone: +27 11 123 4567

---

**🎉 Congratulations! Your landing page is now live on Azure!** 🚀
