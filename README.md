# 🌸 3D Blumen Viewer

Eine minimalistische 3D-Webseite zum Betrachten einer animierten Blume mit Three.js.

## ✨ Features

- **Schwarzer Hintergrund** - Minimalistisches Design
- **Interaktive 3D-Ansicht** - Rotieren mit Maus/Touch
- **Auto-Rotation** - Dreht sich sanft automatisch
- **GLTF-Animationen** - Modell-Animationen werden abgespielt
- **Responsive** - Funktioniert auf Desktop, Tablet und Mobile
- **Touch Support** - Volle Touch-Unterstützung für Smartphones

## 🚀 Live Demo auf GitHub Pages

Diese Webapp ist optimiert für GitHub Pages und läuft direkt im Browser - kein Setup nötig!

## 📁 Projektstruktur

```
versuch blume 2/
├── index.html              # Haupt-Webapp (137 Zeilen)
├── models/
│   └── Animationblume.glb  # 3D-Modell
└── README.md               # Diese Datei
```

## 🎮 Steuerung

- **🖱️ Maus:** Links-Klick + Ziehen zum Rotieren
- **🔍 Mausrad:** Zoom in/out
- **📱 Touch:** Finger ziehen zum Rotieren, Pinch zum Zoomen
- **⚡ Auto-Rotate:** Aktiviert, Geschwindigkeit 1.0

## 🌐 GitHub Pages Deployment

### Schritt 1: Repository erstellen

1. Gehe zu [GitHub](https://github.com) und erstelle ein neues Repository
2. Name z.B. `blumen-3d-viewer` (ohne Leerzeichen)
3. **Public** Repository wählen
4. **OHNE** README, .gitignore oder License erstellen

### Schritt 2: Dateien hochladen

**Option A - Über GitHub Website:**
1. Klicke auf "uploading an existing file"
2. Ziehe alle Dateien in den Browser:
   - `index.html`
   - `README.md`
   - Den kompletten `models/` Ordner
3. Commit Message: "Initial commit"
4. Klicke "Commit changes"

**Option B - Mit Git (Terminal):**
```bash
cd "/Users/bene/Desktop/mac juli 25/25 webapp septem/medien5/versuch blume 2"
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/DEIN-USERNAME/DEIN-REPO-NAME.git
git push -u origin main
```

### Schritt 3: GitHub Pages aktivieren

1. Gehe zu deinem Repository auf GitHub
2. Klicke auf **Settings** (Zahnrad-Icon)
3. Scrolle runter zu **Pages** (linke Seitenleiste)
4. Unter "Source":
   - Branch: **main** auswählen
   - Folder: **/ (root)** auswählen
5. Klicke **Save**
6. Warte 1-2 Minuten

### Schritt 4: Deine Live-URL

Deine Seite ist verfügbar unter:
```
https://DEIN-USERNAME.github.io/DEIN-REPO-NAME/
```

Beispiel:
```
https://bene.github.io/blumen-3d-viewer/
```

## 🔧 Lokale Entwicklung

### Mit VS Code Live Server:
1. Öffne `index.html` in VS Code
2. Rechtsklick → "Open with Live Server"
3. Fertig!

### Mit Python Server:
```bash
python3 -m http.server 8000
```
Dann öffne: `http://localhost:8000`

### Mit Node.js http-server:
```bash
npx http-server -p 8000
```

## ⚙️ Technische Details

- **Three.js:** r128 (von CDN)
- **GLTF Loader:** Für .glb Dateien
- **OrbitControls:** Kamera-Steuerung
- **Keine Build-Tools:** Läuft direkt im Browser
- **Dateigröße:** ~5 KB HTML + GLTF-Modell

## 🎨 Anpassungen

### Modell austauschen:
Ersetze `models/Animationblume.glb` mit deinem eigenen GLTF/GLB Modell.

### Objektgröße ändern:
In `index.html` Zeile ~99:
```javascript
const scale = (3 / maxDim) * 1.44; // Zahl anpassen
```

### Beleuchtung ändern:
In `index.html` Zeilen ~52-62:
```javascript
const ambientLight = new THREE.AmbientLight(0xffffff, 1.0);
const light1 = new THREE.DirectionalLight(0xffffff, 0.8);
```

### Hintergrundfarbe ändern:
In `index.html` Zeile 34:
```javascript
scene.background = new THREE.Color(0x000000); // Schwarz
```
Beispiele:
- `0xffffff` = Weiß
- `0x1a1a2e` = Dunkelblau
- `0x2d3436` = Dunkelgrau

### Auto-Rotation Geschwindigkeit:
In `index.html` Zeile 68:
```javascript
controls.autoRotateSpeed = 1.0; // Höher = schneller
```

### Kamera-Position:
In `index.html` Zeile 43:
```javascript
camera.position.set(0, 0, 8); // x, y, z
```

## 📱 Browser-Kompatibilität

- ✅ Chrome/Edge (empfohlen)
- ✅ Firefox
- ✅ Safari (Desktop & Mobile)
- ✅ Mobile Browser (iOS Safari, Chrome Mobile)
- ⚠️ IE11 wird nicht unterstützt

## 🐛 Troubleshooting

### Modell wird nicht angezeigt:
- Öffne Browser Console (F12)
- Prüfe ob `models/Animationblume.glb` existiert
- Verwende einen lokalen Server (kein `file://` Protokoll)

### Schwarzer Bildschirm:
- Prüfe Browser Console auf Fehler
- Stelle sicher dass Three.js CDN erreichbar ist
- Prüfe ob WebGL unterstützt wird: [webglreport.com](https://webglreport.com)

### Modell ist verschoben:
Das Modell wird automatisch zentriert. Falls Probleme auftreten:
- Exportiere das Modell mit Ursprung bei (0,0,0)
- Prüfe die Skalierung im 3D-Programm

## 📄 Lizenz

Frei verwendbar für persönliche und kommerzielle Projekte.

## 🙋 Support

Bei Fragen oder Problemen öffne ein Issue auf GitHub!

---

**Erstellt mit ❤️ und Three.js**

Deployment-Ready ✅ | GitHub Pages Optimized 🚀 | Mobile-Friendly 📱
