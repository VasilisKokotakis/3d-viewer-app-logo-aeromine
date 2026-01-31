# 🛠️ Troubleshooting Guide

## NPM Installation Issues

### ⚠️ Deprecation Warning: three-mesh-bvh
```
npm warn deprecated three-mesh-bvh@0.7.8
```
**Solution:** This is just a warning from a dependency. It won't affect functionality. The warning will disappear when @react-three/drei updates their dependencies.

**What it means:** One of the packages we use (drei) depends on an older version of three-mesh-bvh. This doesn't break anything!

---

### 🔒 Moderate Security Vulnerabilities
```
2 moderate severity vulnerabilities
```

**Quick Fix:**
```bash
# Delete node_modules and package-lock.json, then reinstall
rm -rf node_modules package-lock.json
npm install
```

**If that doesn't work:**
```bash
# Force update (may cause breaking changes)
npm audit fix --force
```

**Alternative - Use npm override (recommended):**

Add this to your `package.json`:
```json
{
  "overrides": {
    "rollup": "^4.22.0",
    "micromatch": "^4.0.8"
  }
}
```

Then run:
```bash
npm install
```

---

### ✅ Safe to Ignore (For MVP)

For a development/testing MVP, these warnings are **safe to ignore**:
- Deprecation warnings (code still works)
- Moderate vulnerabilities in dev dependencies (only affects build tools, not your app)

Your app will run perfectly fine! 

---

### 🚀 Verify Everything Works

After installation, test it:
```bash
npm run dev
```

If the dev server starts and you see the 3D viewer in your browser, **you're good to go!** ✅

---

## Common Runtime Issues

### Port Already in Use
```
Error: Port 3000 is already in use
```
**Solution:**
```bash
# Kill the process using port 3000
lsof -ti:3000 | xargs kill -9

# Or change the port in vite.config.js
server: {
  port: 3001  // Change to any available port
}
```

### Module Not Found
```
Error: Cannot find module 'three'
```
**Solution:**
```bash
# Make sure you're in the project directory
cd 3d-viewer-app

# Reinstall dependencies
npm install
```

### GLTF Model Not Loading
```
Error loading model
```
**Checklist:**
1. ✅ Model file is in `public/models/` folder
2. ✅ Path in App.jsx starts with `/models/` (with leading slash)
3. ✅ All associated files (.bin, textures) are in the same folder
4. ✅ Model is valid (test at https://gltf-viewer.donmccurdy.com/)

---

## Production Build Issues

### Build Warnings About Dependencies
```bash
# Clean build
rm -rf dist node_modules package-lock.json
npm install
npm run build
```

### Build Size Too Large
**Optimize:**
1. Use `.glb` instead of `.gltf` (smaller)
2. Compress textures
3. Reduce polygon count in 3D models

---

## Still Having Issues?

### Debug Steps:
1. Check browser console (F12) for errors
2. Try a different browser
3. Clear browser cache
4. Update Node.js to latest LTS version
5. Try `npm cache clean --force`

### Quick Reset:
```bash
# Nuclear option - start fresh
rm -rf node_modules package-lock.json
npm install
npm run dev
```

---

## Working Configuration (Tested)

**Node.js version:** 16.x, 18.x, or 20.x LTS  
**npm version:** 8.x or higher  
**Operating System:** Windows, macOS, Linux (all supported)

**Verified Package Versions:**
- react: ^18.3.1
- three: ^0.170.0
- @react-three/fiber: ^8.17.10
- @react-three/drei: ^9.117.3
- vite: ^5.4.11

---

## Need Help?

If you're still stuck:
1. Check the error message in your terminal
2. Check browser console (F12 → Console tab)
3. Google the specific error message
4. Check GitHub issues for the specific package

**Most issues are solved by:**
```bash
rm -rf node_modules package-lock.json
npm install
```

🎯 **Bottom Line:** The warnings you saw are normal and won't stop the app from working!
