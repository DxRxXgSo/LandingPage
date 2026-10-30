# Rutitas — Landing Page

Landing page de presentación para Rutitas, una aplicación móvil universitaria de movilidad compartida que sigue en desarrollo. La página resume el propósito del proyecto, presenta una vista ilustrativa y reserva el acceso por QR hasta que exista un enlace oficial.

## Tecnologías

- React 19 y TypeScript
- Vite 6
- `qrcode.react` para generar el QR cuando se configura una URL HTTPS oficial
- CSS responsive

## Requisitos

- Node.js 20.19+ o 22.12+
- npm

## Desarrollo local

```bash
npm ci
npm run dev
```

Vite mostrará la dirección local en la terminal.

## Verificación y compilación

```bash
npm run typecheck
npm run build
npm run preview
```

La compilación estática se genera en `dist/`.

## Configurar el QR

La URL se configura con `VITE_APP_URL`. Copia `.env.example` como `.env` y reemplaza el valor vacío sólo cuando exista una URL oficial pública con HTTPS:

```env
VITE_APP_URL=https://enlace-oficial-de-la-app
```

Reinicia el servidor o vuelve a compilar después de cambiarla. Sin una URL válida, la landing muestra **“Muy pronto”** y no inventa un QR ni un enlace de descarga. Las variables `VITE_*` se incorporan al sitio público durante la compilación; no deben contener secretos.

## GitHub Pages

El proyecto configura Vite con la base `/LandingPage/` para el repositorio `DxRxXgSo/LandingPage`. El workflow `.github/workflows/deploy.yml` compila `dist/` y solicita su publicación en GitHub Pages al actualizar `main`.

En el repositorio, selecciona **Settings → Pages → Build and deployment → Source → GitHub Actions** si Pages aún no tiene ese origen. El primer despliegue puede tardar unos minutos. La URL prevista del proyecto es <https://dxrxxgso.github.io/LandingPage/>; sólo se considera publicada cuando GitHub Actions confirme el despliegue y la página responda correctamente.

## Estado

Landing visual y responsive para presentar una aplicación móvil universitaria en desarrollo. El mockup usa contenido ilustrativo; no representa viajes, reservas ni disponibilidad reales. La aplicación no se anuncia como publicada en Google Play.
