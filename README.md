# Nakami Trading — Funded Tracker

Versión simplificada del Funded Tracker de NQ Project, adaptada para la comunidad **Nakami Trading**.

## Qué se quitó respecto a la versión original (NQ Project)
- Recompensas (racha / monedas)
- Eventos / Comunidad
- Trader Pro (grupos de cuentas y el filtro de grupo del Dashboard)
- Notas
- Botón flotante de contacto (WhatsApp/Instagram)
- Modal promocional "Opera en vivo — NQ PROJECT"

Se conserva: Dashboard, Cuentas, Diario de Trades, Análisis, Calculadora, Retiros,
tema claro/gris/oscuro, paletas de color, gestor emocional, sistema de mantras,
perfil de usuario, y la campanita de **Novedades** (anuncios internos).

## ⚠️ Antes de publicar — 3 cosas por hacer

### 1. Firebase (obligatorio, la app no funciona sin esto)
Crea un proyecto **nuevo** en [Firebase Console](https://console.firebase.google.com/):
1. Activa **Authentication → Google** como proveedor de acceso.
2. Activa **Firestore Database** (modo producción).
3. Ve a *Configuración del proyecto → Tus apps → Config* y copia los 6 valores.
4. Ábre `index.html`, busca el bloque `firebaseConfig` (línea ~13) y reemplaza:

```js
const firebaseConfig = {
  apiKey:"REEMPLAZAR_API_KEY",
  authDomain:"REEMPLAZAR.firebaseapp.com",
  projectId:"REEMPLAZAR_PROJECT_ID",
  storageBucket:"REEMPLAZAR.firebasestorage.app",
  messagingSenderId:"REEMPLAZAR_SENDER_ID",
  appId:"REEMPLAZAR_APP_ID"
};
```

5. En **Firestore → Reglas**, configura las reglas de seguridad (pídeme ayuda con esto
   cuando tengas el proyecto creado — hay que replicar la lógica de "cada usuario
   solo lee/escribe sus propios documentos" que tenía el proyecto original).

### 2. WhatsApp real de Nakami
Busca `wa.me/50000000000` (aparece 2 veces) y reemplázalo por el link real de
WhatsApp de Nakami/Jaime, ej: `https://wa.me/57XXXXXXXXXX`.

### 3. Instagram real
Busca `nakamitrading` (aparece 2 veces: login y sidebar) y reemplázalo por el
usuario real de Instagram de Nakami.

## Estructura
```
nakami-trading-tracker/
├── index.html          ← toda la app (single-file)
├── assets/
│   └── nakami-logo.png ← logo fénix, fondo transparente
└── README.md
```

## Publicar en GitHub Pages
1. Crea el repo `nakami-trading-tracker` en GitHub.
2. Sube estos 3 elementos (index.html, carpeta assets, README.md).
3. Settings → Pages → Deploy from branch → `main` / `root`.
4. (Opcional) Configura un dominio propio en GoDaddy con un registro CNAME,
   igual que hiciste con los subdominios de nqproject.app.
