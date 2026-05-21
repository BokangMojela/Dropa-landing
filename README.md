# 🌐 Dropa Landing Page

Professional marketing website for Dropa delivery service.

## 🎯 Features

- **Modern Design** - Clean, professional UI with smooth animations
- **Fully Responsive** - Works perfectly on desktop, tablet, and mobile
- **Fast Loading** - Optimized for performance
- **SEO Friendly** - Meta tags and semantic HTML
- **Accessible** - WCAG compliant

## 📋 Sections

1. **Hero** - Eye-catching headline with CTAs
2. **Features** - 6 key features with icons
3. **How It Works** - 3-step process
4. **Pricing** - 3 pricing tiers
5. **Testimonials** - Customer reviews
6. **CTA** - Final call-to-action
7. **Footer** - Links, contact info, social media

## 🚀 Deploy to Azure Static Web Apps (Free)

### **Method 1: Azure Portal (Easiest)**

1. **Go to:** https://portal.azure.com
2. **Search for:** "Static Web Apps"
3. **Click:** "Create"
4. **Configure:**
   ```
   Subscription: Your subscription
   Resource Group: Create new "dropa-rg"
   Name: dropa-landing
   Region: East US 2
   Source: Other
   ```
5. **Click:** "Review + Create"
6. **After creation:**
   - Click "Upload" in the overview page
   - Drag and drop all files from `landing-page` folder
   - Wait 1-2 minutes
   - Your site is live!

### **Method 2: Azure CLI**

```bash
# Install Azure CLI
# https://docs.microsoft.com/en-us/cli/azure/install-azure-cli

# Login
az login

# Create resource group
az group create --name dropa-rg --location eastus2

# Create static web app
az staticwebapp create \
  --name dropa-landing \
  --resource-group dropa-rg \
  --location eastus2

# Deploy
az staticwebapp upload \
  --name dropa-landing \
  --resource-group dropa-rg \
  --source .
```

### **Method 3: GitHub Actions (Automated)**

1. Push code to GitHub
2. In Azure Portal, create Static Web App
3. Connect to GitHub repository
4. Azure automatically sets up CI/CD
5. Every push deploys automatically

## 🌐 Your Live URL

After deployment, your site will be available at:
```
https://dropa-landing.azurestaticapps.net
```

Or configure custom domain:
```
https://www.dropa.co.za
```

## 📱 Links to Apps

The landing page links to:
- **Customer App:** https://dropa-customer.netlify.app
- **Driver App:** https://dropa-driver.netlify.app
- **Admin Dashboard:** https://dropa-admin.netlify.app

## 🎨 Customization

### **Update Links:**
Edit `index.html` and replace URLs:
```html
<a href="YOUR_CUSTOMER_APP_URL">Order Delivery</a>
<a href="YOUR_DRIVER_APP_URL">Become a Driver</a>
```

### **Update Colors:**
Edit `styles.css`:
```css
:root {
    --primary: #10b981; /* Change to your brand color */
}
```

### **Update Content:**
Edit `index.html` to change:
- Hero title and description
- Features
- Pricing
- Testimonials
- Contact information

## 📊 Analytics (Optional)

Add Google Analytics by inserting before `</head>`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 🔧 Local Development

Simply open `index.html` in your browser, or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve

# Using PHP
php -S localhost:8000
```

Then visit: http://localhost:8000

## 📦 Files Structure

```
landing-page/
├── index.html              # Main HTML file
├── styles.css              # All styles
├── script.js               # JavaScript functionality
├── staticwebapp.config.json # Azure configuration
├── .gitignore              # Git ignore rules
└── README.md               # This file
```

## ✅ Checklist Before Going Live

- [ ] Update all app URLs
- [ ] Add real app screenshots
- [ ] Update contact information
- [ ] Test on mobile devices
- [ ] Test all links
- [ ] Add Google Analytics (optional)
- [ ] Configure custom domain (optional)
- [ ] Set up SSL certificate (automatic on Azure)

## 🎉 Features

- ✅ Responsive design
- ✅ Smooth animations
- ✅ Mobile menu
- ✅ Scroll effects
- ✅ Counter animations
- ✅ Parallax effects
- ✅ SEO optimized
- ✅ Fast loading
- ✅ Cross-browser compatible

## 📞 Support

For issues or questions:
- Email: support@dropa.co.za
- Phone: +27 11 123 4567

---

**Built with ❤️ for Dropa**
