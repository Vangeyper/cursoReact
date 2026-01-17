# Habilidades del agente

Una colección de habilidades para agentes de programación con IA. Las habilidades son instrucciones y scripts empaquetados que amplían las capacidades del agente.

Las habilidades siguen el formato de [Habilidades del agente](https://agentskills.io/).

## Habilidades disponibles

### react-mejores-prácticas

Guías de optimización de rendimiento para React y Next.js creadas por Vercel Engineering. Contiene más de 40 reglas en 8 categorías, priorizadas por impacto.

**Utilizar cuando:**
- Escribiendo nuevos componentes de React o páginas de Next.js
- Implementando data fetching (en cliente o servidor)
- Revisando código en busca de problemas de rendimiento
- Optimizando el tamaño del bundle o los tiempos de carga

**Categorías cubiertas:**
- Eliminación de waterfalls (Crítico)
- Optimización del tamaño del bundle (Crítico)
- Rendimiento del lado del servidor (Alto)
- Data fetching del lado del cliente (Medio-Alto)
- Optimización de re-renderizados (Medio)
- Rendimiento de renderizado (Medio)
- Micro-optimizaciones de JavaScript (Bajo-Medio)

### directrices-de-diseño-web

Revisa código de UI para comprobar el cumplimiento de buenas prácticas de interfaces web. Audita tu código con más de 100 reglas que cubren accesibilidad, rendimiento y UX.

**Utilizar cuando:**
- "Review my UI"
- "Check accessibility"
- "Audit design"
- "Review UX"
- "Check my site against best practices"

**Categorías cubiertas:**
- Accesibilidad (aria-labels, HTML semántico, controladores de teclado)
- Estados de foco (focus visible, patrones focus-visible)
- Formularios (autocomplete, validación, manejo de errores)
- Animación (prefers-reduced-motion, transforms compatibles con compositor)
- Tipografía (comillas tipográficas, puntos suspensivos, tabular-nums)
- Imágenes (dimensiones, lazy loading, texto alternativo)
- Rendimiento (virtualización, layout thrashing, preconnect)
- Navegación y estado (la URL refleja el estado, deep-linking)
- Modo oscuro y theming (color-scheme, meta theme-color)
- Interacción táctil (touch-action, tap-highlight)
- Localización e i18n (Intl.DateTimeFormat, Intl.NumberFormat)

### vercel-desplegar-reclamable

Despliega aplicaciones y sitios web en Vercel al instante. Diseñado para usarse con claude.ai y Claude Desktop para permitir despliegues directamente desde conversaciones. Los despliegues son "reclamables": los usuarios pueden transferir la propiedad a su propia cuenta de Vercel.

**Utilizar cuando:**
- "Deploy my app"
- "Deploy this to production"
- "Push this live"
- "Deploy and give me the link"

**Características:**
- Detecta automáticamente más de 40 frameworks desde `package.json`
- Devuelve una URL de preview (sitio en vivo) y una URL de reclamación (transferencia de propiedad)
- Maneja proyectos HTML estáticos automáticamente
- Excluye `node_modules` y `.git` de las subidas

**Cómo funciona:**
1. Empaqueta tu proyecto en un archivo tarball
2. Detecta el framework (Next.js, Vite, Astro, etc.)
3. Sube el proyecto al servicio de despliegue
4. Devuelve la URL de preview y la URL de reclamación

**Salida:**
```
Implementación correcta!

Preview URL: https://skill-deploy-abc123.vercel.app
Claim URL:   https://vercel.com/claim-deployment?code=...
```

## Instalación

```bash
npx add-skill vercel-labs/agent-skills
```

## Uso

Las habilidades están disponibles automáticamente una vez instaladas. El agente las utilizará cuando detecte tareas relevantes.

**Ejemplos:**
```
Implementar mi aplicación
```
```
Revisa este componente React para detectar problemas de rendimiento.
```
```
Ayúdame a optimizar esta página de Next.js.
```

## Estructura de habilidades

Cada habilidad contiene:
- `SKILL.md` - Instrucciones para el agente
- `scripts/` - Scripts auxiliares para la automatización (opcional)
- `references/` - Documentación de respaldo (opcional)

## Licencia

MIT
