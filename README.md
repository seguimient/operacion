README
# 🚗 Control Operacional Vehicular

Sistema empresarial de inspección pre-operacional de vehículos, auditoría de flota y gestión de taller. Aplicación web **100% client-side** (sin backend), lista para usar y desplegar en **GitHub Pages**.

![Estado](https://img.shields.io/badge/estado-activo-16a34a)
![Licencia](https://img.shields.io/badge/licencia-MIT-2563eb)
![Dependencias](https://img.shields.io/badge/dependencias-0-7c3aed)
![PWA](https://img.shields.io/badge/PWA-offline-0ea5e9)

---

## ✨ Características

- **Inspección vehicular en 4 pasos**: Vehículo → Inventario → Novedades → Registros.
- **22 ítems de inventario** evaluables (extintor, botiquín, kit de carretera, luces, etc.).
- **+90 tipos de hallazgos** agrupados por categoría (motor, frenos, carrocería, eléctrico, etc.).
- **Evidencia fotográfica** con compresión automática en canvas (máx. 4 fotos por novedad).
- **Cálculo automático del estado**: 🟢 Apto · 🟡 Requiere revisión · 🔴 No apto.
- **Dashboard en vivo** con donut chart, bar chart y gauge (SVG puro, sin librerías).
- **Informe empresarial imprimible** con portada, gráficas, firmas y hash de verificación.
- **Informe general consolidado** de toda la flota.
- **PWA instalable y offline** (Service Worker + manifest).
- **Persistencia local** con `localStorage` (sin servidor).
- **Diseño responsive** y animaciones fluidas.

---

## 🚀 Demo

Una vez publicado en GitHub Pages:

```
https://TU-USUARIO.github.io/control-operacional-vehicular/
```

---

## 🛠️ Uso local

No requiere instalación ni build. Solo abre `index.html`:

```bash
# Opción 1: doble clic sobre index.html
# Opción 2: servidor local rápido
python -m http.server 8000
# → http://localhost:8000
```

> El Service Worker requiere servirse por HTTP/HTTPS (no funciona abriendo `file://`).

---

## 📦 Despliegue en GitHub Pages

### Opción A — Automático (recomendado)

El repositorio incluye `.github/workflows/deploy.yml`. Solo:

1. Sube los archivos a la rama `main`.
2. Ve a **Settings → Pages → Source: GitHub Actions**.
3. Cada `push` desplegará automáticamente.

### Opción B — Manual

1. **Settings → Pages**.
2. Source: `Deploy from a branch`.
3. Branch: `main` / folder: `/ (root)`.
4. Guarda y espera ~1 minuto.

---

## 🧭 Flujo de trabajo

| Paso | Pestaña | Acción |
|------|---------|--------|
| 1 | 🚙 Vehículo | Datos del conductor, vehículo y responsables |
| 2 | 🧰 Inventario | Evaluar los 22 ítems (Bueno / Regular / Malo / Faltante / N/A) |
| 3 | ⚠️ Novedades | Registrar hallazgos con severidad, prioridad, fotos y costo |
| 4 | 📋 Registros | Historial, filtros, ver informe, imprimir, borrar |

### Reglas del estado global

- 🔴 **No apto**: ≥1 novedad crítica o ≥2 implementos mal/faltantes.
- 🟡 **Requiere revisión**: novedades moderadas/leves o implementos regulares.
- 🟢 **Apto**: todo en orden.

---

## 🧱 Estructura

```
.
├── index.html                    # App completa (HTML + CSS + JS inline)
├── manifest.json                 # Manifiesto PWA
├── sw.js                         # Service Worker (offline)
├── icon.svg                      # Ícono de la aplicación
├── README.md
├── LICENSE
├── .gitignore
└── .github/
    └── workflows/
        └── deploy.yml            # Deploy automático a GitHub Pages
```

---

## 🔒 Privacidad

- **No se envía ningún dato a servidores externos.**
- Toda la información vive en el `localStorage` del navegador del usuario.
- Las fotos se comprimen localmente antes de guardarse.

---

## 🗺️ Roadmap

- [ ] Exportar registros a Excel/CSV.
- [ ] Sincronización opcional con backend (Supabase / Firebase).
- [ ] Múltiples usuarios y roles.
- [ ] Firma digital en canvas.
- [ ] Modo multi-idioma.

---

## 📄 Licencia

MIT © 2025 — Ver [LICENSE](./LICENSE).
