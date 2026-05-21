# 🔗 Connect Azure Static Web App to GitHub

Your code is now on GitHub! Now let's connect it to Azure for automatic deployment.

**GitHub Repo:** https://github.com/BokangMojela/Dropa-landing
**Azure Site:** https://black-tree-012b9fb03.7.azurestaticapps.net

---

## 🚀 Connect via Azure Portal (3 minutes)

### **Step 1: Open Azure Portal**
1. Go to: https://portal.azure.com
2. Search for "Dropa" in the top search bar
3. Click on your Static Web App "Dropa"

### **Step 2: Configure GitHub Deployment**
1. In the left menu, click **"Deployment"** or **"Configuration"**
2. Look for **"Source"** or **"Deployment source"**
3. Click **"GitHub"**
4. You'll be prompted to authorize Azure
5. Click **"Authorize Azure Static Web Apps"**
6. Sign in to GitHub if needed

### **Step 3: Select Repository**
1. **Organization:** BokangMojela
2. **Repository:** Dropa-landing
3. **Branch:** main

### **Step 4: Build Configuration**
1. **Build Presets:** Custom
2. **App location:** `/` (or leave blank)
3. **Api location:** (leave blank)
4. **Output location:** (leave blank)

### **Step 5: Save and Deploy**
1. Click **"Save"** or **"Review + create"**
2. Azure will automatically:
   - Create a GitHub Actions workflow
   - Commit it to your repo
   - Start the first deployment
3. Wait 2-3 minutes for deployment

### **Step 6: Verify Deployment**
1. Go to: https://github.com/BokangMojela/Dropa-landing/actions
2. You should see a workflow running
3. Wait for it to complete (green checkmark)
4. Visit: https://black-tree-012b9fb03.7.azurestaticapps.net
5. Your landing page should be live!

---

## 🔄 Future Updates

After this setup, updating your site is easy:

```bash
cd c:\Users\user\Documents\Apps\Dropa\landing-page

# Make your changes to index.html, styles.css, etc.

git add .
git commit -m "Update landing page"
git push

# Automatically deploys in 2-3 minutes!
```

---

## ✅ What Happens Next

Once connected:
- ✅ Every push to `main` branch auto-deploys
- ✅ GitHub Actions handles the build
- ✅ Site updates in 2-3 minutes
- ✅ Free CI/CD pipeline
- ✅ Deployment history in GitHub Actions

---

## 🎉 Your URLs

**GitHub Repo:** https://github.com/BokangMojela/Dropa-landing
**Live Site:** https://black-tree-012b9fb03.7.azurestaticapps.net

---

**Follow the steps above to complete the connection!** 🚀
