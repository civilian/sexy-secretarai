# Plan de aprendizaje para entender el proyecto

## Resumen del stack
- Electron: procesos `main`, `preload`, `renderer`; IPC con `contextBridge`, `ipcMain`/`ipcRenderer`; empaquetado con Electron Forge; entitlements/firmado en macOS.
- TypeScript: tipado estricto en `main`, `preload` y React.
- React 18: componentes con hooks y composición de vistas.
- Zustand: estado global en el renderer.
- Vite: configuración multi-bundle (`main`, `preload`, `renderer`).
- Tailwind CSS v4 + PostCSS.
- Node.js APIs: `fs`, `path`, `child_process`, etc.
- Google GenAI (`@google/genai`): sesiones Live (audio/stream), herramientas y mensajes.
- Captura de media: `getUserMedia`, captura de pantalla y audio, integración con Electron.
- Tooling: `pnpm`, Biome (format), Oxlint (lint), `clsx`, `lucide-react`.

## Orden sugerido (checklist)
1. [ ] Electron (procesos, IPC seguro, Forge y makers, empaquetado/firmado)
2. [ ] TypeScript + React (hooks, tipado de props/estado)
3. [ ] Zustand (patrones de store y persistencia)
4. [ ] Vite multi-target (configs para `main`, `preload`, `renderer`)
5. [ ] Tailwind CSS v4 (utilidades y buenas prácticas)
6. [ ] Google GenAI Live + captura de audio/pantalla

## Archivos clave a leer
- [ ] `README.md`
- [ ] `src/main/index.ts`
- [ ] `src/preload/index.ts`
- [ ] `src/renderer/App.tsx`
- [ ] `src/renderer/stores/appStore.ts`
- [ ] `src/main/gemini/GeminiService.ts`
- [ ] `src/main/window/WindowManager.ts`
- [ ] `vite.main.config.ts`, `vite.preload.config.ts`, `vite.renderer.config.ts`
- [ ] `forge.config.ts`

## Tareas prácticas
- [ ] Instalar Node LTS y `pnpm`
- [ ] `pnpm install`
- [ ] `pnpm start`
- [ ] Crear API Key de Gemini en [Google AI Studio](https://aistudio.google.com/apikey) e introducirla en la app
- [ ] Probar “Start Session” y comprobar respuestas en tiempo real
- [ ] Leer y anotar cada archivo clave (sección anterior)
- [ ] Configurar captura de audio del sistema en macOS (ver `assets/SystemAudioDump`)
- [ ] Probar atajos de teclado (mover ventana, click-through, enviar)
- [ ] Empaquetar con `pnpm make` (opcional) y revisar artefactos

## Recursos útiles
- Electron: https://www.electronjs.org/docs/latest
- Electron Forge: https://www.electronforge.io/
- Vite (Electron plugin): https://www.electronforge.io/plugins/vite
- React 18: https://react.dev
- Zustand: https://docs.pmnd.rs/zustand
- Tailwind v4: https://tailwindcss.com/docs
- Google GenAI (Node): https://ai.google.dev/gemini-api/docs

## Notas
- En macOS, los permisos y entitlements (micro) están configurados en `entitlements.plist` y `forge.config.ts` (packagerConfig). Si firmas para distribución, revisa requisitos de Apple.
- La app usa `@google/genai` con sesiones Live; revisa `src/main/gemini/GeminiService.ts` para entender el flujo de audio y mensajes.


