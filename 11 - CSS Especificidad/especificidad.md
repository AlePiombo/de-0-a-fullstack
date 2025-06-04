# Especificidad en CSS - Guía Completa

## ¿Qué es la Especificidad?

La especificidad en CSS es un sistema de puntuación que determina qué reglas de estilo se aplican cuando múltiples selectores apuntan al mismo elemento. Es fundamental para entender por qué algunas reglas CSS se aplican y otras no.

## Cómo Funciona la Especificidad

La especificidad se calcula usando un sistema de cuatro categorías, representado como: **a, b, c, d**

### Pirámide de Especificidad

```
                    !important
                   /           \
                  /             \
                 /               \
                /     1000 pts     \
               /   Estilos Inline   \
              /_____________________ \
             /                       \
            /         100 pts         \
           /           IDs             \
          /___________________________ \
         /                             \
        /            10 pts             \
       /  Clases, Atributos, Pseudo-c   \
      /_______________________________ \
     /                                 \
    /              1 pt                \
   /    Elementos y Pseudo-elementos   \
  /_____________________________________\
 /                                       \
/              0 pts                      \
\_____  Selector Universal (*)  _________/

```

**Lectura de la pirámide:** Mientras más arriba en la pirámide, mayor especificidad. Los estilos en niveles superiores siempre vencen a los de niveles inferiores, sin importar la cantidad.

### Sistema de Puntuación

| Categoría | Valor | Descripción |
|-----------|--------|-------------|
| **a** | 1000 | Estilos inline (style="...") |
| **b** | 100 | IDs (#id) |
| **c** | 10 | Clases (.class), atributos ([type="text"]), pseudo-clases (:hover) |
| **d** | 1 | Elementos (div, p, h1) y pseudo-elementos (::before, ::after) |

## Ejemplos de Cálculo

```css
/* Especificidad: 0,0,0,1 = 1 punto */
p { color: red; }

/* Especificidad: 0,0,1,0 = 10 puntos */
.texto { color: blue; }

/* Especificidad: 0,1,0,0 = 100 puntos */
#titulo { color: green; }

/* Especificidad: 0,0,1,1 = 11 puntos */
p.texto { color: orange; }

/* Especificidad: 0,1,1,1 = 111 puntos */
#titulo.texto p { color: purple; }

/* Especificidad: 1,0,0,0 = 1000 puntos */
<p style="color: black;">Texto</p>
```

## Reglas de Especificidad

### 1. Mayor Especificidad Gana
El selector con mayor especificidad siempre prevalece:

```css
/* Especificidad: 0,0,0,1 = 1 */
p { color: red; }

/* Especificidad: 0,0,1,0 = 10 - GANA */
.azul { color: blue; }
```

### 2. En Caso de Empate, Gana el Último
Si dos selectores tienen la misma especificidad, se aplica el que aparece último en el CSS:

```css
.texto { color: red; }
.texto { color: blue; } /* Este se aplica */
```

### 3. Los Selectores Universales No Cuentan
```css
/* Especificidad: 0,0,0,0 */
* { margin: 0; }

/* Especificidad: 0,0,1,0 */
*.clase { color: red; } /* El * no suma */
```

## Casos Especiales

### !important
La declaración `!important` anula la especificidad normal:

```css
/* Especificidad: 0,0,0,1 + !important */
p { color: red !important; }

/* Especificidad: 0,1,0,0 - NO se aplica debido al !important anterior */
#titulo { color: blue; }
```

**Nota:** Solo otro `!important` con mayor especificidad puede anular un `!important`.

### Estilos Inline
Los estilos inline tienen la mayor especificidad (excepto por `!important`):

```html
<!-- Especificidad: 1,0,0,0 -->
<p style="color: red;">Este texto será rojo</p>
```

```css
/* Especificidad: 0,1,0,0 - NO se aplica */
#parrafo { color: blue; }
```

## Selectores Complejos - Ejemplos Detallados

### Selectores de Atributo
```css
/* Especificidad: 0,0,1,1 = 11 */
input[type="text"] { border: 1px solid gray; }

/* Especificidad: 0,0,2,1 = 21 */
input[type="text"].activo { border: 2px solid blue; }
```

### Pseudo-clases y Pseudo-elementos
```css
/* Especificidad: 0,0,1,1 = 11 */
a:hover { color: red; }

/* Especificidad: 0,0,0,2 = 2 */
p::before { content: "→"; }

/* Especificidad: 0,0,1,2 = 12 */
p.destacado::after { content: "★"; }
```

### Selectores de Descendientes
```css
/* Especificidad: 0,0,0,3 = 3 */
div p span { color: red; }

/* Especificidad: 0,1,1,2 = 112 */
#contenedor .texto p { color: blue; }

/* Especificidad: 0,2,0,1 = 201 */
#header #nav a { color: green; }
```

## Herramientas para Calcular Especificidad

### Calculadora Mental Rápida
1. Cuenta los IDs: multiplica por 100
2. Cuenta las clases, atributos y pseudo-clases: multiplica por 10
3. Cuenta los elementos y pseudo-elementos: multiplica por 1
4. Suma todo

### Ejemplo Práctico
```css
/* #nav .menu li a:hover */
/* IDs: 1 × 100 = 100 */
/* Clases: 1 × 10 = 10 */
/* Pseudo-clases: 1 × 10 = 10 */
/* Elementos: 2 × 1 = 2 */
/* Total: 100 + 10 + 10 + 2 = 122 */
```

## Mejores Prácticas

### ✅ Recomendado
- Usar clases para la mayoría de estilos
- Mantener la especificidad baja y consistente
- Organizar CSS de menor a mayor especificidad
- Evitar `!important` en lo posible

### ❌ Evitar
- Usar muchos IDs en selectores
- Abusar de `!important`
- Crear selectores excesivamente específicos
- Mezclar estilos inline con CSS externo

## Estrategias de Organización

### Metodología BEM
```css
/* Bloque */
.menu { }

/* Elemento */
.menu__item { }

/* Modificador */
.menu__item--activo { }
```

### Especificidad Progresiva
```css
/* Base: 0,0,0,1 */
button { }

/* Variante: 0,0,1,0 */
.btn-primary { }

/* Estado: 0,0,2,0 */
.btn-primary.disabled { }

/* Contexto: 0,0,2,1 */
.modal .btn-primary { }
```

## Debugging de Especificidad

### Herramientas del Navegador
1. **Inspector de Elementos**: Muestra qué reglas se aplican y cuáles están sobrescritas
2. **Computed Styles**: Muestra el valor final calculado
3. **Cascada**: Visualiza el orden de aplicación de reglas

### Técnicas de Debug
```css
/* Temporal: Usar bordes para identificar elementos */
.debug { border: 2px solid red !important; }

/* Usar colores de fondo únicos */
.test-especificidad { background: lime !important; }
```

## Casos de Uso Comunes

### Reset vs Normalize
```css
/* Reset básico - baja especificidad */
* { margin: 0; padding: 0; }

/* Estilos específicos - mayor especificidad */
.contenido p { margin-bottom: 1rem; }
```

### Responsive Design
```css
/* Base */
.grid { display: flex; }

/* Modificador responsive */
@media (max-width: 768px) {
  .grid--mobile { flex-direction: column; }
}
```

### Estados de Componentes
```css
/* Estado base */
.boton { background: blue; }

/* Estado hover - misma especificidad, orden importa */
.boton:hover { background: darkblue; }

/* Estado activo */
.boton.activo { background: green; }

/* Estado deshabilitado - mayor especificidad */
.boton.activo.deshabilitado { background: gray; }
```

## Conclusión

La especificidad es un concepto fundamental en CSS que determina qué estilos se aplican a los elementos. Comprender cómo funciona te permite escribir CSS más predecible y mantenible. La clave está en mantener la especificidad baja y consistente, usar una metodología clara de nomenclatura, y evitar soluciones rápidas como `!important` que pueden crear problemas a largo plazo.

Recordar siempre: **a mayor especificidad, mayor prioridad**, y en caso de empate, **gana el último en orden de aparición**.