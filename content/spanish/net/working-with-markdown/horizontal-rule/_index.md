---
title: Regla horizontal
linktitle: Regla horizontal
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo insertar una regla horizontal con Aspose.Words para .NET Guía paso a paso.
type: docs
weight: 10
url: /es/net/working-with-markdown/horizontal-rule/
---

En este ejemplo, le mostraremos cómo utilizar la función de regla horizontal con Aspose.Words para .NET. La regla horizontal se utiliza para separar visualmente secciones de un documento.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: Insertar una regla horizontal

 Podemos insertar una regla horizontal usando el`InsertHorizontalRule` método del generador de documentos.

```csharp
builder. InsertHorizontalRule();
```

## Código fuente de muestra para regla horizontal con Aspose.Words para .NET

```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Insertar regla horizontal.
builder.InsertHorizontalRule();
```

¡Enhorabuena! Ahora ha aprendido a utilizar la función de regla horizontal con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo creo una regla horizontal en Markdown?

R: Para crear una regla horizontal en Markdown, puedes usar uno de los siguientes símbolos en una línea vacía: tres asteriscos (\***), tres guiones (\---), o tres guiones bajos (\___).

#### P: ¿Puedo personalizar la apariencia de una regla horizontal en Markdown?

R: En Markdown estándar, no hay forma de personalizar la apariencia de las reglas horizontales. Sin embargo, algunos editores y extensiones avanzados de Markdown ofrecen funciones de personalización adicionales.

#### P: ¿Todos los editores de Markdown admiten reglas horizontales?

R: Sí, los editores de Markdown más populares admiten reglas horizontales. Sin embargo, siempre es mejor consultar la documentación de su proveedor específico para asegurarse de que sea compatible.

#### P: ¿Qué otros elementos puedo crear en Markdown?

R: Además de las reglas horizontales, puedes crear títulos, párrafos, listas, enlaces, imágenes, tablas y más en Markdown.