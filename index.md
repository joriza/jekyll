# Guía para configurar Jekyll en GitHub Pages

## 🧰 Requisitos previos

- Tener una cuenta en [GitHub](https://github.com/)
- Tener creado un repositorio (por ejemplo: `https://github.com/tuusuario/jekyll`)
- Tener instalado Ruby y Jekyll si se quiere previsualizar localmente (opcional)

---

## 🏗️ Estructura básica del proyecto

Si el contenido está en la **raíz del repositorio**, debe verse así:

```
jekyll/
├── _config.yml
├── index.md
├── _layouts/
├── _posts/
└── ...
```

Si lo vas a publicar desde la carpeta `/docs`, la estructura será:

```
jekyll/
└── docs/
    ├── _config.yml
    ├── index.md
    ├── _layouts/
    ├── _posts/
    └── ...
```

---

## ⚙️ Configuración de GitHub Pages

1. Ir a **Settings > Pages** del repositorio.
2. En **"Source"**, seleccionar:
   - Branch: `main` (o el que estés usando)
   - Folder: `/` (root) o `/docs`, según corresponda
3. Guardar y esperar unos segundos.

---

## 🧾 Archivo `_config.yml`

Debe estar en la **raíz del proyecto** o en la carpeta `/docs` si se usa como fuente. Ejemplo básico:

```yaml
title: "Mi sitio con Jekyll"
theme: minima  # o cualquier tema soportado
baseurl: "/jekyll"  # nombre del repositorio
url: "https://tuusuario.github.io"
```

> ⚠️ `baseurl` debe coincidir con el nombre del repositorio si no usás un repo tipo `tuusuario.github.io`.

---

## 🎨 Cambiar el tema del sitio

GitHub Pages solo permite usar [temas compatibles](https://pages.github.com/themes/), como:

- `minima`
- `slate`
- `cayman`
- `architect`
- `hacker`, etc.

Para cambiarlo, en `_config.yml`:

```yaml
theme: slate
```

---

## 📝 Archivos Markdown

### Página de inicio

Debe llamarse obligatoriamente:

- `index.md` o
- `index.html`

Para que se publique como página principal del sitio.

### Páginas secundarias

Podés tener archivos como:

- `about.md`
- `contacto.md`

Se acceden en:

```
https://tuusuario.github.io/repositorio/about.html
```

Podés personalizar la URL usando `permalink`:

```markdown
---
layout: default
title: Sobre mí
permalink: /sobre/
---

# Sobre mí
Soy docente y programador...
```

Esto crea la página en:

```
https://tuusuario.github.io/repositorio/sobre/
```

---

## 🚀 Publicar cambios

Cada vez que actualices el sitio:

```bash
git add .
git commit -m "Actualizo el sitio"
git push origin main
```

---

## 🔗 URL final

El sitio se publicará en:

```
https://tuusuario.github.io/nombre-del-repositorio/
```

> Si el repositorio se llama `tuusuario.github.io`, se publicará directamente en la raíz del dominio:
> ```
> https://tuusuario.github.io/
> ```

---

## ✅ Buenas prácticas

- Siempre tener un `index.md` o `index.html`.
- Usar `layout: default` en tus archivos markdown.
- Probar distintos temas cambiando `theme:` en `_config.yml`.
- Usar `baseurl` correctamente si tu sitio no está en la raíz.

---

