---
$title: Incluir iframes
$order: 2
$category: Develop 
components:
  - iframe
toc: true
---
[TOC]

Descubre cómo incluir contenido multimedia en tus páginas y cómo usar iframes para mostrar contenido avanzado saltándose las limitaciones de AMP.

## Aspectos básicos

Incluye un iframe en tu página usando el elemento 
[`amp-iframe`](/es/docs/reference/components/amp-iframe.html).

Los iframes son especialmente útiles en AMP para mostrar contenido que no se admita en 
la página principal, como el contenido que requiere JavaScript creado por usuarios.

### Requisitos de `amp-iframe`

* Debe tener al menos **600 píxeles** o un **75%** de la primera ventana gráfica si empezamos por el principio de la página.
* Solo puede solicitar recursos por HTTPS, y estos no deben tener el mismo origen que el contenedor salvo que no se especifique allow-same-origin.

{% call callout('Leer más', type='read') %}
Obtén más información [en la especificación completa de <code>amp-iframe</code>](/es/docs/reference/components/amp-iframe.html). 
{% endcall %}

### Incluir la secuencia de comandos

Para incluir un `amp-iframe` en tu página, 
primero debe constar la siguiente secuencia de comandos en el `<head>`, que carga el código adicional del componente ampliado:

[sourcecode:html]
<script async custom-element="amp-iframe"
    src="https://cdn.ampproject.org/v0/amp-iframe-0.1.js"></script>
[/sourcecode]

### Escribir las etiquetas

Un ejemplo de `amp-iframe`:

```html
<amp-iframe width="200" height="100"
    sandbox="allow-scripts allow-same-origin"
    layout="responsive"
    src="https://www.google.com/maps/embed/v1/place?key=AIzaSyDG9YXIhKBhqclZizcSzJ0ROiE0qgVfwzI&q=europe">
</amp-iframe>
```

Preview: 

<amp-iframe width="200" height="100"
    sandbox="allow-scripts allow-same-origin"
    layout="responsive"
    src="https://www.google.com/maps/embed/v1/place?key=AIzaSyDG9YXIhKBhqclZizcSzJ0ROiE0qgVfwzI&q=europe">
</amp-iframe>

## Usar elementos placeholder

Puedes mostrar un `amp-iframe` en la parte superior de un documento siempre y cuando el atributo `placeholder` se incluya en algún elemento de `amp-iframe` como, (por ejemplo, `amp-img`). Este elemento se renderizará como un marcador de posición hasta que el iframe esté listo para mostrarse.

{% call callout('Leer más', type='read') %}
Obtén más información sobre los elementos placeholder en la sección [Iframes con elementos placeholder](/es/docs/reference/components/amp-iframe.html#iframe-with-placeholder).
{% endcall %}


Este ejemplo de un elemento placeholder:

```html
<amp-iframe width="400" height="225"
sandbox="allow-scripts allow-same-origin"
layout="responsive"
src="https://giphy.com/embed/OWabwoEn7ezug">
<amp-img placeholder layout="fill"
src="https://ampproject-b5f4c.firebaseapp.com/examples/images/kittens-biting.jpg"></amp-img>
</amp-iframe>
```
Aparecerá así:

<amp-iframe width="400" height="225"
sandbox="allow-scripts allow-same-origin"
layout="responsive"
src="https://giphy.com/embed/OWabwoEn7ezug">
<amp-img placeholder layout="fill"
src="https://ampproject-b5f4c.firebaseapp.com/examples/images/kittens-biting.jpg"></amp-img>
</amp-iframe>

## Ejemplos

Puedes encontrar más ejemplos avanzados en la página de nuestra [demostración avanzada](https://ampbyexample.com/components/amp-iframe/).
