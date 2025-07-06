
# 🚀 Frontend de Truckly

Este directorio contiene el frontend de **Truckly**, una SPA moderna y eficiente para la gestión y visualización de flotas vehiculares. Está desarrollado en **React + TypeScript** y construido con **Vite**, aprovechando el tipado estricto, modularidad de componentes y herramientas de desarrollo modernas.

---

## 📂 Estructura de Carpetas y Archivos

```bash
.
├── components.json            # Configuración de componentes o generación automática
├── eslint.config.js           # Configuración de ESLint
├── index.html                 # Documento HTML raíz de la app
├── package.json               # Dependencias y scripts del frontend
├── public                     # Archivos públicos y estáticos (favicon, logos, etc.)
├── src                        # Código fuente principal
│   ├── assets                 # Imágenes y recursos multimedia
│   ├── components             # Componentes reutilizables de la UI y vistas principales
│   │   ├── conductor          # Componentes específicos del panel de conductor
│   │   │   ├── assignments    # Lista, tarjetas y formularios de asignaciones del conductor
│   │   │   └── maintenance    # Visualización e historial de mantenciones
│   │   ├── dashboard         # Componentes del dashboard de administración
│   │   │   ├── forms         # Formularios para CRUD de usuarios, vehículos y asignaciones
│   │   │   ├── navigation    # Navegación lateral, menú y secciones
│   │   │   │   └── sections.ts # Definición de secciones y rutas del dashboard
│   │   │   └── tables        # Tablas para visualizar datos: asignaciones, usuarios, vehículos
│   │   └── ui                # Componentes de interfaz genéricos (inputs, modals, botones, etc.)
│   ├── hooks                  # Custom hooks para lógica compartida
│   │   ├── query             # Hooks de consultas a API (ej: usuarios)
│   │   └── use-mobile.ts     # Hook para detectar dispositivos móviles
│   ├── index.css              # Estilos globales
│   ├── lib                    # Librerías utilitarias y helpers
│   │   ├── auth-client.ts    # Cliente de autenticación y helpers de sesión
│   │   ├── auth-store.ts     # Almacenamiento y gestión de estado de autenticación
│   │   ├── clients.ts        # Configuración de clientes externos (ej: trpc)
│   │   ├── trpc.ts           # Configuración del cliente tRPC
│   │   └── utils
│   │       └── cn.ts         # Función utilitaria para concatenar clases
│   ├── routes                 # Definición de rutas y vistas principales (conductor y dashboard)
│   │   ├── conductor
│   │   └── dashboard
│   ├── routeTree.gen.ts       # Archivo generado automáticamente para el árbol de rutas
│   ├── types.d.ts             # Definiciones globales de tipos TypeScript
│   └── vite-env.d.ts          # Tipos de entorno de Vite
├── tsconfig.app.json          # Configuración de TypeScript para la app
├── tsconfig.json              # Configuración principal de TypeScript
├── tsconfig.node.json         # Configuración de TypeScript para scripts node
└── vite.config.ts             # Configuración de Vite (build, plugins, etc.)
```

---

## 🛠️ Tecnologías y Herramientas Principales

- **React + TypeScript:** Desarrollo de interfaces robustas y componetizadas.
- **Vite:** Bundler ultrarrápido con soporte HMR para desarrollo ágil.
- **TanStack Router:** Enrutamiento dinámico para la SPA.
- **Zod:** Validación estricta en formularios y flujos críticos.
- **tRPC:** Comunicación directa y type-safe con el backend.
- **Autenticación integrada:** Manejo de sesión y permisos según rol (admin/conductor).
- **ESLint:** Linter avanzado y configuración flexible para mantener calidad de código.

---

## ⚡ Instalación y Ejecución Local

1. **Instala las dependencias:**
    ```sh
    bun install
    ```

2. **Inicia el frontend en modo desarrollo:**
    ```sh
    bun run client:dev
    ```

3. Abre tu navegador en:  
   [http://localhost:5173](http://localhost:5173)

---

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config({
  extends: [
    // Remove ...tseslint.configs.recommended and replace with this
    ...tseslint.configs.recommendedTypeChecked,
    // Alternatively, use this for stricter rules
    ...tseslint.configs.strictTypeChecked,
    // Optionally, add this for stylistic rules
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config({
  plugins: {
    // Add the react-x and react-dom plugins
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // other rules...
    // Enable its recommended typescript rules
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
})
```