# 🚀 QUICK START GUIDE

## Get Running in 3 Minutes!

### Step 1: Install Dependencies
```bash
cd 3d-viewer-app
npm install
```

### Step 2: Add Your Model
Put your GLTF files in the `public/models/` folder:

```
public/
└── models/
    ├── your-model.gltf    # Your main model file
    ├── your-model.bin     # Binary data (if separate)
    └── textures/          # Texture images (if any)
        └── *.png
```

### Step 3: Update Model Path
Edit `src/App.jsx` line 7:
```javascript
const [modelPath, setModelPath] = useState('/models/your-model.gltf')
//                                              ^^^ Change this
```

### Step 4: Run!
```bash
npm run dev
```

That's it! Your browser will open with the 3D viewer.

---

## 🎯 Controls

- **Rotate**: Left click + drag
- **Pan**: Right click + drag  
- **Zoom**: Mouse wheel

---

## 🧪 Test Without Your Model

Don't have a GLTF model yet? Download a free one:

1. Go to https://sketchfab.com/features/gltf
2. Find a model you like (make sure it has "Download" button)
3. Download as GLTF format
4. Extract and copy files to `public/models/`
5. Update the path in App.jsx

---

## 💡 Key Files

- **`src/App.jsx`** - Main app, change model path here
- **`src/components/ModelViewer.jsx`** - 3D canvas settings (camera, lights)
- **`src/components/Model.jsx`** - Loads and displays the GLTF model
- **`public/models/`** - Put all your 3D files here

---

## 🛠️ Common Adjustments

### Make model bigger/smaller
`src/components/Model.jsx` line 32:
```javascript
const scale = 2 / maxDim  // Increase 2 to make bigger
```

### Change background color
`src/App.css` line 6:
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

### Remove grid
`src/components/ModelViewer.jsx` - Delete line 52:
```javascript
<gridHelper args={[10, 10]} />  // ← Delete this line
```

### Enable auto-rotation
`src/components/Model.jsx` line 42 - Uncomment:
```javascript
groupRef.current.rotation.y += 0.001
```

---

## ❓ Need Help?

Check the full README.md for detailed documentation!
