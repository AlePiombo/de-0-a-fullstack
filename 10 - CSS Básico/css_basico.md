# CSS Básico - Selectores y Propiedades

## ¿Qué es CSS?
CSS (Cascading Style Sheets) es un lenguaje de estilos que define la presentación visual de documentos HTML. Permite separar el contenido de la presentación.

## Sintaxis Básica
```css
selector {
    propiedad: valor;
    propiedad: valor;
}
```

## Selectores Básicos

### Selector de Elemento
Selecciona todos los elementos de un tipo específico.
```css
p {
    color: blue;
}
h1 {
    font-size: 24px;
}
```

### Selector de Clase
Selecciona elementos con una clase específica (precedido por `.`).
```css
.mi-clase {
    background-color: yellow;
}
.texto-grande {
    font-size: 18px;
}
```

### Selector de ID
Selecciona un elemento con un ID específico (precedido por `#`).
```css
#mi-id {
    border: 1px solid red;
}
#header {
    width: 100%;
}
```

### Selector Universal
Selecciona todos los elementos.
```css
* {
    margin: 0;
    padding: 0;
}
```

## Selectores Combinados

### Selector Descendiente
Selecciona elementos dentro de otros elementos.
```css
div p {
    color: green;
}
.container h2 {
    text-align: center;
}
```

### Selector de Hijo Directo
Selecciona elementos hijos directos (con `>`).
```css
ul > li {
    list-style: none;
}
```

### Selector de Hermano Adyacente
Selecciona el elemento que sigue inmediatamente (con `+`).
```css
h1 + p {
    margin-top: 0;
}
```

## Propiedades de Texto

### Color y Fuente
```css
.texto {
    color: #333333;           /* Color del texto */
    font-family: Arial, sans-serif;  /* Familia de fuente */
    font-size: 16px;          /* Tamaño de fuente */
    font-weight: bold;        /* Grosor: normal, bold, 100-900 */
    font-style: italic;       /* Estilo: normal, italic, oblique */
}
```

### Alineación y Decoración
```css
.texto-centrado {
    text-align: center;       /* left, right, center, justify */
    text-decoration: underline; /* none, underline, line-through */
    line-height: 1.5;         /* Altura de línea */
    letter-spacing: 2px;      /* Espaciado entre letras */
}
```

## Propiedades de Fondo

### Color y Imagen de Fondo
```css
.fondo {
    background-color: #f0f0f0;
    background-image: url('imagen.jpg');
    background-repeat: no-repeat;  /* repeat, repeat-x, repeat-y */
    background-position: center;   /* top, bottom, left, right, center */
    background-size: cover;        /* contain, cover, auto */
}
```

## Modelo de Caja (Box Model)

### Propiedades del Modelo de Caja
```css
.caja {
    width: 300px;             /* Ancho */
    height: 200px;            /* Alto */
    padding: 20px;            /* Espacio interior */
    margin: 10px;             /* Espacio exterior */
    border: 2px solid black;  /* Borde */
}
```

### Padding (Relleno)
```css
.padding-ejemplo {
    padding: 10px;            /* Todos los lados */
    padding: 10px 20px;       /* Vertical | Horizontal */
    padding: 10px 15px 20px 25px; /* Arriba | Derecha | Abajo | Izquierda */
    padding-top: 10px;        /* Solo arriba */
    padding-right: 15px;      /* Solo derecha */
}
```

### Margin (Margen)
```css
.margin-ejemplo {
    margin: 10px;             /* Todos los lados */
    margin: 10px auto;        /* Vertical | Horizontal (auto centra) */
    margin-bottom: 20px;      /* Solo abajo */
    margin-left: auto;        /* Solo izquierda */
}
```

### Border (Borde)
```css
.borde-ejemplo {
    border: 1px solid red;    /* Grosor | Estilo | Color */
    border-width: 2px;        /* Grosor */
    border-style: dashed;     /* solid, dashed, dotted, double */
    border-color: blue;       /* Color */
    border-radius: 10px;      /* Esquinas redondeadas */
}
```

## Propiedades de Posicionamiento

### Display
```css
.display-ejemplo {
    display: block;           /* block, inline, inline-block, none */
}
```

### Position
```css
.posicion {
    position: static;         /* static, relative, absolute, fixed */
    top: 10px;               /* Distancia desde arriba */
    left: 20px;              /* Distancia desde izquierda */
    right: 15px;             /* Distancia desde derecha */
    bottom: 5px;             /* Distancia desde abajo */
}
```

### Float
```css
.flotante {
    float: left;              /* left, right, none */
    clear: both;              /* left, right, both, none */
}
```

## Propiedades de Lista

### Estilos de Lista
```css
ul {
    list-style-type: disc;    /* disc, circle, square, decimal, none */
    list-style-position: inside; /* inside, outside */
    list-style-image: url('bullet.png'); /* Imagen personalizada */
}
```

## Pseudoclases Comunes

### Estados de Enlaces
```css
a:link {                     /* Enlace no visitado */
    color: blue;
}
a:visited {                  /* Enlace visitado */
    color: purple;
}
a:hover {                    /* Al pasar el mouse */
    color: red;
}
a:active {                   /* Al hacer clic */
    color: orange;
}
```

### Otras Pseudoclases
```css
.elemento:first-child {      /* Primer hijo */
    font-weight: bold;
}
.elemento:last-child {       /* Último hijo */
    margin-bottom: 0;
}
.elemento:nth-child(2) {     /* Segundo hijo */
    background-color: gray;
}
```

## Unidades de Medida

### Unidades Absolutas
- `px` - Píxeles
- `pt` - Puntos
- `cm` - Centímetros
- `mm` - Milímetros

### Unidades Relativas
- `%` - Porcentaje relativo al elemento padre
- `em` - Relativo al tamaño de fuente del elemento
- `rem` - Relativo al tamaño de fuente del elemento raíz
- `vw` - Porcentaje del ancho de la ventana
- `vh` - Porcentaje de la altura de la ventana

## Formas de Incluir CSS

### CSS Inline
```html
<p style="color: red; font-size: 16px;">Texto con estilo</p>
```

### CSS Interno
```html
<head>
    <style>
        p { color: blue; }
    </style>
</head>
```

### CSS Externo
```html
<head>
    <link rel="stylesheet" href="estilos.css">
</head>
```

## Colores en CSS

### Formatos de Color
```css
.colores {
    color: red;               /* Nombre del color */
    color: #ff0000;           /* Hexadecimal */
    color: #f00;              /* Hexadecimal corto */
    color: rgb(255, 0, 0);    /* RGB */
    color: rgba(255, 0, 0, 0.5); /* RGBA con transparencia */
    color: hsl(0, 100%, 50%); /* HSL */
}
```

## Consejos Importantes

### Especificidad
El orden de especificidad (de mayor a menor):
1. Estilos inline
2. IDs
3. Clases y pseudoclases
4. Elementos

### Herencia
Muchas propiedades se heredan del elemento padre al hijo, como `color`, `font-family`, etc.

### Cascada
Los estilos se aplican en cascada, donde los últimos definidos tienen prioridad (a igual especificidad).