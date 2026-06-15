# Deployment Guide

## GitHub Pages Deployment

### Step 1: Enable GitHub Pages

1. Go to your repository settings
2. Navigate to **Settings** → **Pages**
3. Under **Source**, select **Deploy from a branch**
4. Select **main** branch and **/ (root)** folder
5. Click **Save**

Your site will be available at: `https://kanakadhara850-blip.github.io/DataForge_CMS/`

### Step 2: Configure Firebase

1. Create a Firebase project at [firebase.google.com](https://firebase.google.com)
2. In **Project Settings**, copy your config
3. Update `js/firebase-config.js`:

```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

### Step 3: Configure Firestore

1. In Firebase Console, enable **Firestore Database**
2. Start in **Production mode**
3. Create collections:
   - `events`
   - `registrations`
   - `announcements`
   - `admins`
   - `categories`

### Step 4: Configure Authentication

1. Go to **Authentication** → **Sign-in method**
2. Enable **Email/Password**
3. Add admin user manually or programmatically

### Step 5: Configure Storage

1. Go to **Storage**
2. Click **Get Started**
3. Use default security rules (or update them)

### Step 6: Deploy Security Rules

Update Firestore security rules from `firebase/security-rules.json`

### Step 7: Deploy to GitHub Pages

```bash
# Clone repository
git clone https://github.com/kanakadhara850-blip/DataForge_CMS.git
cd DataForge_CMS

# Make changes
git add .
git commit -m "Your message"
git push origin main
```

GitHub Pages will automatically deploy within seconds.

## Custom Domain

1. Buy a domain
2. Add domain in **GitHub Pages settings**
3. Update DNS records:
   - A records pointing to GitHub's IPs
   - Or use CNAME for subdomain

## Performance Optimization

- Images are lazy-loaded
- CSS and JS are minified
- Use CDN for Firebase SDKs
- Enable caching headers

## Monitoring

- Check Firebase Console for errors
- Monitor GitHub Pages status
- Use browser DevTools for client-side issues

## Troubleshooting

### Firebase Not Working
- Verify config is correct
- Check browser console for errors
- Ensure security rules allow access

### Images Not Loading
- Verify Storage paths are correct
- Check CORS settings in Storage
- Ensure URLs are publicly accessible

### CORS Issues
- Update Firebase Storage CORS rules
- Use proper headers in requests
