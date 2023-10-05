---
title: Lista con viñetas
linktitle: Lista con viñetas
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear una lista con viñetas con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/bulleted-list/
---

En este tutorial, le diremos cómo crear una lista con viñetas con Aspose.Words para .NET. Una lista con viñetas se utiliza para enumerar elementos sin utilizar numeración.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: aplicar una lista con viñetas predeterminada

 Podemos aplicar una lista con viñetas predeterminada utilizando la función del generador de documentos.`ApplyBulletDefault` método.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Paso 3: Personalizar el formato de viñeta

Podemos personalizar el formato de viñeta accediendo a las propiedades de`ListFormat.List.ListLevels[0]`. En este ejemplo, utilizamos el guión "-" como viñeta.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Paso 4: Agregar elementos a la lista

 Ahora podemos agregar elementos a la lista con viñetas usando la herramienta del generador de documentos.`Writeln` método.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Paso 5: eliminar la sangría de la lista

 Si queremos crear una sublista, podemos aumentar la sangría usando el`ListFormat.ListIndent()` método. En este ejemplo, agregamos una sublista a los elementos 2a y 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Código fuente de ejemplo para la lista con viñetas usando Aspose.Words para .NET


```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

¡Enhorabuena! Ahora ha aprendido cómo crear una lista con viñetas con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo crear una lista con viñetas en Markdown?

R: Para crear una lista con viñetas en Markdown, comience cada elemento de la lista con un símbolo de viñeta (`-`, `*` , o`+`), seguido de un espacio.

#### P: ¿Se pueden anidar listas con viñetas en Markdown?

R: Sí, es posible anidar listas con viñetas en Markdown agregando cuatro espacios de desplazamiento delante de cada elemento de la lista anidada.

#### P: ¿Cómo personalizar los símbolos de viñetas?

R: En Markdown estándar, los símbolos de viñetas están predefinidos. Sin embargo, algunos editores de Markdown te permiten personalizarlos usando extensiones específicas.

#### P: ¿Las listas con viñetas en Markdown admiten sangría?

R: Sí, las listas con viñetas en Markdown admiten sangría. Puede agregar un desplazamiento a la izquierda usando espacios o tabulaciones.

#### P: ¿Se pueden agregar enlaces o texto en línea a los elementos de la lista?

R: Sí, puede agregar enlaces o texto en línea para enumerar elementos utilizando la sintaxis de Markdown adecuada.
