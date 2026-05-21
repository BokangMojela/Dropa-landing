# 🚀 Quick Deploy to Your Azure Static Web App

**Your Site:** https://black-tree-012b9fb03.7.azurestaticapps.net

The SWA CLI is having issues with the deployment binary. Here are 2 simple alternatives:

---

## ✅ Option 1: Deploy via GitHub (EASIEST - 5 minutes)

This is the recommended method - it's automated and works perfectly.

### **Step 1: Create GitHub Repo**
```bash
# Go to: https://github.com/new
# Repository name: dropa-landing
# Make it Public
# Don't initialize with anything
# Click "Create repository"
```

### **Step 2: Push Your Code**
```bash
cd c:\Users\user\Documents\Apps\Dropa\landing-page

git init
git add .
git commit -m "Dropa landing page"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/dropa-landing.git
git push -u origin main
```

### **Step 3: Connect to Azure**
1. Go to: https://portal.azure.com
2. Find your Static Web App "Dropa"
3. Click "Deployment" → "GitHub"
4. Authorize GitHub
5. Select repository: `dropa-landing`
6. Branch: `main`
7. Build Presets: `Custom`
8. App location: `/`
9. Leave API and Output empty
10. Click "Save"

**Done!** GitHub Actions will deploy automatically in 2-3 minutes.

---

## ✅ Option 2: Manual ZIP Upload via Portal

### **Step 1: Create Deployment Package**

1. Open: `c:\Users\user\Documents\Apps\Dropa\landing-page`
2. Select these files ONLY:
   - index.html
   - styles.css
   - script.js
3. Right-click → "Send to" → "Compressed (zipped) folder"
4. Name it: `dropa-landing.zip`

### **Step 2: Upload via Azure Portal**

1. Go to: https://portal.azure.com
2. Navigate to your "Dropa" Static Web App
3. Click "Overview"
4. Look for "Browse" or deployment options
5. If you see an upload option, use it
6. Otherwise, go to "Deployment" → "Manual deployment"

**Note:** Azure Static Web Apps primarily uses GitHub/Azure DevOps for deployment. Manual upload might not be available in the free tier.

---

## ✅ Option 3: Use Azure Storage Static Website (Alternative)

If GitHub deployment doesn't work, you can use Azure Storage:

### **Create Storage Account:**
```bash
az storage account create \
  --name dropalanding \
  --resource-group Dropa \
  --location eastus2 \
  --sku Standard_LRS \
  --kind StorageV2

az storage blob service-properties update \
  --account-name dropalanding \
  --static-website \
  --index-document index.html
```

### **Upload Files:**
```bash
az storage blob upload-batch \
  --account-name dropalanding \
  --source . \
  --destination '$web'
```

### **Get URL:**
```bash
az storage account show \
  --name dropalanding \
  --resource-group Dropa \
  --query "primaryEndpoints.web" \
  --output tsv
```

---

## 🎯 Recommended: Use Option 1 (GitHub)

**Why?**
- ✅ Works 100% of the time
- ✅ Automatic deployments
- ✅ Version control
- ✅ Easy updates (just push)
- ✅ Free CI/CD
- ✅ Takes only 5 minutes

**After deployment, your landing page will be live at:**
https://black-tree-012b9fb03.7.azurestaticapps.net

---

## 📞 Need Help?

If you don't have a GitHub account:
1. Sign up at: https://github.com/join
2. It's free and takes 2 minutes
3. Then follow Option 1 above

---

**Let me know which option you'd like to use and I'll help you through it!** 🚀
