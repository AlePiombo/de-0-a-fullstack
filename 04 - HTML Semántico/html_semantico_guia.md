# Guía de HTML Semántico - Etiquetas y Uso

## ¿Qué es HTML Semántico?

HTML semántico se refiere al uso de etiquetas HTML que tienen significado y propósito específico, no solo para la presentación visual, sino para describir el contenido de manera meaningful para navegadores, motores de búsqueda y tecnologías de asistencia.

## Estructura Principal del Documento

### `<html>`
- **Uso**: Elemento raíz que contiene todo el contenido de la página
- **Ejemplo**: `<html lang="es">`

### `<head>`
- **Uso**: Contiene metadatos sobre el documento
- **Ejemplo**: `<head>` - incluye título, meta tags, enlaces a CSS, etc.

### `<body>`
- **Uso**: Contiene todo el contenido visible de la página
- **Ejemplo**: `<body>` - todo lo que ve el usuario

## Etiquetas de Estructura Semántica

### `<header>`
- **Uso**: Encabezado de una página o sección
- **Contenido típico**: Logo, navegación principal, título principal
- **Ejemplo**:
```html
<header>
    <h1>Mi Sitio Web</h1>
    <nav>...</nav>
</header>
```

### `<nav>`
- **Uso**: Sección de navegación con enlaces principales
- **Contenido típico**: Menús de navegación, breadcrumbs
- **Ejemplo**:
```html
<nav>
    <ul>
        <li><a href="/">Inicio</a></li>
        <li><a href="/productos">Productos</a></li>
    </ul>
</nav>
```

### `<main>`
- **Uso**: Contenido principal único de la página
- **Nota**: Solo debe haber un `<main>` por página
- **Ejemplo**:
```html
<main>
    <h1>Contenido Principal</h1>
    <p>Este es el contenido más importante...</p>
</main>
```

### `<section>`
- **Uso**: Sección temática de contenido con su propio encabezado
- **Cuándo usar**: Cuando el contenido puede tener su propio título
- **Ejemplo**:
```html
<section>
    <h2>Servicios</h2>
    <p>Ofrecemos los siguientes servicios...</p>
</section>
```

### `<article>`
- **Uso**: Contenido independiente y reutilizable
- **Contenido típico**: Posts de blog, noticias, comentarios
- **Ejemplo**:
```html
<article>
    <h2>Título del Artículo</h2>
    <p>Contenido del artículo...</p>
    <time datetime="2024-01-15">15 de enero, 2024</time>
</article>
```

### `<aside>`
- **Uso**: Contenido relacionado pero secundario
- **Contenido típico**: Sidebar, publicidad, enlaces relacionados
- **Ejemplo**:
```html
<aside>
    <h3>Artículos Relacionados</h3>
    <ul>
        <li><a href="#">Artículo 1</a></li>
        <li><a href="#">Artículo 2</a></li>
    </ul>
</aside>
```

### `<footer>`
- **Uso**: Pie de página o de sección
- **Contenido típico**: Copyright, enlaces adicionales, información de contacto
- **Ejemplo**:
```html
<footer>
    <p>&copy; 2024 Mi Empresa. Todos los derechos reservados.</p>
</footer>
```

## Etiquetas de Encabezados

### `<h1>` a `<h6>`
- **Uso**: Jerarquía de títulos y subtítulos
- **Regla**: `<h1>` para el título principal, `<h2>` para secciones, etc.
- **Ejemplo**:
```html
<h1>Título Principal</h1>
<h2>Sección</h2>
<h3>Subsección</h3>
```

## Etiquetas de Contenido Específico

### `<time>`
- **Uso**: Fechas y horas específicas
- **Atributo importante**: `datetime` para formato legible por máquinas
- **Ejemplo**:
```html
<time datetime="2024-12-25">25 de diciembre de 2024</time>
```

### `<address>`
- **Uso**: Información de contacto del autor o propietario
- **Ejemplo**:
```html
<address>
    Escrito por <a href="mailto:autor@email.com">Juan Pérez</a><br>
    Visítanos en: Calle Principal 123, Ciudad
</address>
```

### `<blockquote>`
- **Uso**: Citas largas de otras fuentes
- **Atributo**: `cite` para la URL de la fuente
- **Ejemplo**:
```html
<blockquote cite="https://fuente.com">
    <p>Esta es una cita importante...</p>
</blockquote>
```

### `<cite>`
- **Uso**: Título de una obra citada
- **Ejemplo**:
```html
<p>Como dice en <cite>El Quijote</cite>...</p>
```

### `<figure>` y `<figcaption>`
- **Uso**: Contenido ilustrativo con su descripción
- **Ejemplo**:
```html
<figure>
    <img src="grafico.jpg" alt="Gráfico de ventas">
    <figcaption>Figura 1: Ventas del primer trimestre</figcaption>
</figure>
```

## Etiquetas de Texto Semántico

### `<mark>`
- **Uso**: Texto resaltado por relevancia
- **Ejemplo**: `<mark>texto importante</mark>`

### `<strong>`
- **Uso**: Texto con fuerte importancia
- **Ejemplo**: `<strong>¡Muy importante!</strong>`

### `<em>`
- **Uso**: Énfasis en el texto
- **Ejemplo**: `<em>palabra enfatizada</em>`

### `<small>`
- **Uso**: Texto secundario como disclaimers
- **Ejemplo**: `<small>Términos y condiciones aplican</small>`

### `<abbr>`
- **Uso**: Abreviaciones con su significado completo
- **Ejemplo**: `<abbr title="HyperText Markup Language">HTML</abbr>`

### `<code>`
- **Uso**: Fragmentos de código
- **Ejemplo**: `<code>document.getElementById()</code>`

### `<pre>`
- **Uso**: Texto preformateado
- **Ejemplo**:
```html
<pre>
    Este texto
    mantiene    espacios
    y saltos de línea
</pre>
```

## Etiquetas de Listas Semánticas

### `<dl>`, `<dt>`, `<dd>`
- **Uso**: Listas de definiciones
- **Ejemplo**:
```html
<dl>
    <dt>HTML</dt>
    <dd>Lenguaje de marcado para páginas web</dd>
    <dt>CSS</dt>
    <dd>Hojas de estilo para diseño web</dd>
</dl>
```

## Etiquetas de Formularios Semánticos

### `<fieldset>` y `<legend>`
- **Uso**: Agrupar controles de formulario relacionados
- **Ejemplo**:
```html
<fieldset>
    <legend>Información Personal</legend>
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre">
</fieldset>
```

### `<label>`
- **Uso**: Etiqueta para controles de formulario
- **Ejemplo**: `<label for="email">Email:</label>`

## Etiquetas Multimedia Semánticas

### `<audio>`
- **Uso**: Contenido de audio
- **Ejemplo**:
```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    Tu navegador no soporta audio HTML5.
</audio>
```

### `<video>`
- **Uso**: Contenido de video
- **Ejemplo**:
```html
<video controls width="320" height="240">
    <source src="video.mp4" type="video/mp4">
    Tu navegador no soporta video HTML5.
</video>
```

## Beneficios del HTML Semántico

1. **Accesibilidad**: Los lectores de pantalla pueden navegar mejor el contenido
2. **SEO**: Los motores de búsqueda entienden mejor la estructura y contenido
3. **Mantenimiento**: El código es más legible y fácil de mantener
4. **Consistencia**: Estructura clara y predecible
5. **Futuro**: Preparado para nuevas tecnologías y estándares

## Mejores Prácticas

- Usa siempre la etiqueta más específica y apropiada para el contenido
- Mantén una jerarquía lógica de encabezados (h1 → h2 → h3)
- No uses etiquetas semánticas solo por su apariencia visual
- Incluye atributos relevantes como `lang`, `datetime`, `cite`
- Valida tu HTML para asegurar semántica correcta
- Piensa en cómo las tecnologías de asistencia interpretarán tu contenido

## Ejemplo de Estructura Semántica Completa

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Mi Blog Semántico</title>
</head>
<body>
    <header>
        <h1>Mi Blog Personal</h1>
        <nav>
            <ul>
                <li><a href="/">Inicio</a></li>
                <li><a href="/blog">Blog</a></li>
                <li><a href="/contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article>
            <header>
                <h2>Mi Primer Post</h2>
                <time datetime="2024-01-15">15 de enero, 2024</time>
            </header>
            <p>Contenido del artículo...</p>
            <footer>
                <p>Por <address>Juan Pérez</address></p>
            </footer>
        </article>
    </main>
    
    <aside>
        <section>
            <h3>Posts Populares</h3>
            <ul>
                <li><a href="#">Post 1</a></li>
                <li><a href="#">Post 2</a></li>
            </ul>
        </section>
    </aside>
    
    <footer>
        <p><small>&copy; 2024 Mi Blog. Todos los derechos reservados.</small></p>
    </footer>
</body>
</html>
```

Recuerda: el HTML semántico no se trata solo de usar las etiquetas correctas, sino de crear una estructura de documento que tenga sentido y sea accesible para todos los usuarios y tecnologías.