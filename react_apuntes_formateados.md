# React – Apuntes y conceptos (formato Markdown)

> Apuntes reorganizados y formateados para una lectura cómoda en iPad (Apple Notes, Obsidian, Notion, Bear).

---

## 📌 Qué es React

- Biblioteca de JavaScript creada en **2011**
- Pensada para construir **interfaces gráficas declarativas**
- Previene ataques **XSS** (no renderiza HTML directamente)
- API **estable** y comunidad muy grande
- Se usa en:
  - Web
  - Mobile (React Native)
  - Desktop (Windows / macOS)

---

## 🧠 Imperativo vs Declarativo

### Imperativo (Vanilla JS)
Decimos **cómo** hacer las cosas.

### Declarativo (React)
Decimos **qué** queremos que se muestre.

React está diseñado para trabajar de forma **declarativa**.

---

## 🧱 Renderizado básico

```js
import ReactDOM from "https://esm.sh/react-dom@18.2.0/client"

const root = ReactDOM.createRoot(document.getElementById('app'))
root.render('Un texto')
```

⚠️ Esto **no renderiza HTML**, solo texto (protección XSS).

---

## ⚛️ React.createElement

```js
const button = React.createElement(
  'button',
  { 'data-id': 123 },
  'Guardar'
)

root.render(button)
```

- 1º parámetro: elemento
- 2º parámetro: props
- 3º parámetro: children

---

## 🚫 Renderizar varios elementos

❌ Incorrecto:
```js
root.render(button1, button2)
```

✅ Correcto (con envoltorio):
```js
const div = React.createElement('div', null, [button1, button2])
root.render(div)
```

---

## 🧩 React.Fragment

Evita añadir nodos innecesarios al DOM.

```js
const fragment = React.createElement(
  React.Fragment,
  null,
  [button1, button2, button3]
)
```

En JSX:
```jsx
<>
  <button>Button 1</button>
  <button>Button 2</button>
</>
```

---

## ✨ JSX

- Es **JavaScript**, no HTML
- Se transpila con **Babel o SWC**
- Mucho más legible que `createElement`

```jsx
const name = 'Miguel'
<h1>Hola, {name}</h1>
```

⚠️ Dentro de `{}` solo se permiten **expresiones**, no declaraciones (`if`, `for`, etc.).

---

## 🏷️ Atributos en JSX

- Se usa **camelCase**

```jsx
<button tabIndex="1">Click</button>
```

- `class` → `className`

---

## 📦 Crear proyectos

### Vite (recomendado)
```bash
npm create vite@latest
cd nombre-proyecto
npm install
npm run dev
```

- Detecta JSX automáticamente
- Usa **SWC** (más rápido que Babel)

---

## 🧩 Componentes

```jsx
function Button({ text }) {
  return <button>{text}</button>
}
```

Uso:
```jsx
<Button text="Guardar" />
```

📌 Los componentes:
- Usan **PascalCase**
- Son reutilizables mediante props

---

## 🎨 Estilos

### CSS externo (recomendado)
```js
import './styles.css'
```

### Estilos inline
```jsx
<article style={{ display: 'flex', alignItems: 'center' }} />
```

---

## 🪝 Hooks principales

### useState
- Cambia estado → renderiza

### useRef
- No renderiza
- Útil para:
  - Referencias DOM
  - Flags
  - Valores persistentes

```js
const inputRef = useRef()
```

---

## 🧠 useEffect

- Controla efectos secundarios
- Se ejecuta según dependencias

```js
useEffect(() => {
  // efecto
  return () => {
    // cleanup
  }
}, [deps])
```

---

## ⚡ useMemo

Evita cálculos innecesarios.

```js
const sortedMovies = useMemo(() => {
  return [...movies].sort((a, b) => a.title.localeCompare(b.title))
}, [movies])
```

📌 No abusar de `useMemo`.

---

## 📋 Formularios

### No controlados (recomendado)

```js
const data = Object.fromEntries(new FormData(event.target))
```

- Más eficiente
- Menos renders

### Controlados
- Usan estado
- Más validaciones
- Menos eficientes

---

## 🧭 SPA y navegación

- NO usar botones para navegar
- Usar `<a>` o `<Link>`

```jsx
<a href="/about">About</a>
```

Para SPA:
```jsx
<Link to="/about">About</Link>
```

---

## 🧪 Testing (Playwright)

```js
await expect(textContent.length).toBeGreaterThan(0)
```

---

## 🛠️ Herramientas recomendadas

- React Developer Tools
- ESLint
- Vite
- Playwright

---

## ✅ Consejos clave

- Mantén los componentes limpios
- Extrae lógica a **custom hooks**
- El estado debe ser **mínimo**
- Prefiere composición a lógica compleja

---

📱 **Optimizado para iPad** – lectura fluida, bloques claros y código bien separado

