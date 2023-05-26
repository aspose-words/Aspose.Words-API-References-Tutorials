---
title: Lista con viñetas
linktitle: Lista con viñetas
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear una lista con viñetas con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/bulleted-list/
---

En este tutorial, le diremos cómo crear una lista con viñetas con Aspose.Words para .NET. Una lista con viñetas se usa para enumerar elementos sin usar numeración.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: aplicar una lista con viñetas predeterminada

 Podemos aplicar una lista con viñetas predeterminada usando el generador de documentos`ApplyBulletDefault` método.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Paso 3: Personalización del formato de viñeta

 Podemos personalizar el formato de la viñeta accediendo a las propiedades de`ListFormat.List.ListLevels[0]`. En este ejemplo, usamos el guión "-" como viñeta.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Paso 4: agregar elementos a la lista

 Ahora podemos agregar elementos a la lista con viñetas usando el generador de documentos`Writeln` método.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Paso 5: Eliminar la sangría de la lista

 Si queremos crear una sublista, podemos aumentar la sangría usando el`ListFormat.ListIndent()` método. En este ejemplo, estamos agregando una sublista a los elementos 2a y 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Código fuente de ejemplo para Lista con viñetas usando Aspose.Words para .NET


```csharp
	// Use un generador de documentos para agregar contenido al documento.
	DocumentBuilder builder = new DocumentBuilder();

	builder.ListFormat.ApplyBulletDefault();
	builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();

	builder.Writeln("Item 2a");
	builder.Writeln("Item 2b");
            
```

¡Felicidades! Ahora ha aprendido a crear una lista con viñetas con Aspose.Words para .NET.

