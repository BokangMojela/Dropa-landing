# 🚀 Deploy Your Landing Page to Azure

**Your Azure Static Web App Details:**
- Name: Dropa
- Resource Group: Dropa
- URL: https://black-tree-012b9fb03.7.azurestaticapps.net
- Status: Waiting for deployment

---

## ✅ Method 1: Deploy via GitHub (Recommended - Automated)

### **Step 1: Create GitHub Repository**

1. Go to: https://github.com/new
2. Create a new repository named: `dropa-landing`
3. Make it public or private (your choice)
4. Don't initialize with README

### **Step 2: Push Landing Page to GitHub**

```bash
cd c:\Users\user\Documents\Apps\Dropa\landing-page

# Initialize git
git init
git add .
git commit -m "Initial commit - Dropa landing page"

# Add remote (replace YOUR_USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/dropa-landing.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### **Step 3: Connect Azure to GitHub**

1. Go to: https://portal.azure.com
2. Navigate to your Static Web App "Dropa"
3. Click "Deployment" in the left menu
4. Click "Connect to GitHub"
5. Authorize Azure to access your GitHub
6. Select:
   - Organization: Your GitHub username
   - Repository: dropa-landing
   - Branch: main
7. Build Details:
   - Build Presets: Custom
   - App location: `/`
   - Api location: (leave empty)
   - Output location: (leave empty)
8. Click "Save"

### **Step 4: Wait for Deployment**

- GitHub Actions will automatically build and deploy
- Check progress at: https://github.com/YOUR_USERNAME/dropa-landing/actions
- Takes 2-3 minutes
- Your site will be live at: https://black-tree-012b9fb03.7.azurestaticapps.net

---

## ✅ Method 2: Manual Upload via Azure Portal

### **Step 1: Get Deployment Token**

```bash
az staticwebapp secrets list --name Dropa --resource-group Dropa --query "properties.apiKey" -o tsv
```

Copy the token that appears.

### **Step 2: Install SWA CLI**

```bash
npm install -g @azure/static-web-apps-cli
```

### **Step 3: Deploy**

```bash
cd c:\Users\user\Documents\Apps\Dropa\landing-page

swa deploy --deployment-token "YOUR_TOKEN_HERE" --app-location . --output-location .
```

Replace `YOUR_TOKEN_HERE` with the token from Step 1.

---

## ✅ Method 3: ZIP Upload via Portal

### **Step 1: Create ZIP File**

1. Go to: `c:\Users\user\Documents\Apps\Dropa\landing-page`
2. Select all files:
   - index.html
   - styles.css
   - script.js
   - staticwebapp.config.json
3. Right-click → Send to → Compressed (zipped) folder
4. Name it: `dropa-landing.zip`

### **Step 2: Upload via Azure Portal**

1. Go to: https://portal.azure.com
2. Navigate to your Static Web App "Dropa"
3. Click "Overview"
4. Look for "Upload" or "Deployment" section
5. Upload the ZIP file
6. Wait 1-2 minutes
7. Visit: https://black-tree-012b9fb03.7.azurestaticapps.net

---

## 🎯 Recommended: Use Method 1 (GitHub)

**Why?**
- ✅ Automatic deployments on every push
- ✅ Version control
- ✅ Easy to update (just push changes)
- ✅ Free CI/CD with GitHub Actions
- ✅ Rollback capability

---

## 🧪 After Deployment

### **Test Your Site:**
1. Visit: https://black-tree-012b9fb03.7.azurestaticapps.net
2. Check all sections load
3. Test mobile menu
4. Click all buttons
5. Test on mobile device

### **Update App URLs:**
Once your PWAs are deployed, update the links in `index.html`:
```html
<!-- Replace these URLs with your actual deployed URLs -->
<a href="https://dropa-customer.netlify.app">Customer App</a>
<a href="https://dropa-driver.netlify.app">Driver App</a>
<a href="https://dropa-admin.netlify.app">Admin Dashboard</a>
```

---

## 🔄 Update Your Site (After Initial Deployment)

### **If using GitHub (Method 1):**
```bash
# Make changes to your files
git add .
git commit -m "Update landing page"
git push
# Automatically deploys in 2-3 minutes
```

### **If using SWA CLI (Method 2):**
```bash
swa deploy --deployment-token "YOUR_TOKEN" --app-location . --output-location .
```

---

## 📞 Need Help?

If you encounter issues:
1. Check Azure Portal for deployment logs
2. Verify all files are in the landing-page folder
3. Ensure GitHub repository is accessible
4. Check deployment status in GitHub Actions

---

**Your live URL:** https://black-tree-012b9fb03.7.azurestaticapps.net 🚀
