---
title: Texto en negrita
linktitle: Texto en negrita
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a poner texto en negrita con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/bold-text/
---

En este ejemplo, le diremos cómo poner texto en negrita con Aspose.Words para .NET. El texto en negrita lo hace más visible y le da más protagonismo.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: texto en negrita

 Podemos poner el texto en negrita configurando el generador de documentos`Font.Bold` propiedad a`true`.

```csharp
builder.Font.Bold = true;
```

## Paso 3: Agregar contenido al documento

 Ahora podemos agregar contenido al documento utilizando los métodos del generador de documentos, como`Writeln`, que añade una línea de texto.

```csharp
builder.Writeln("This text will be bold");
```

## Ejemplo de código fuente para texto en negrita usando Aspose.Words para .NET


```csharp
	// Use un generador de documentos para agregar contenido al documento.
	DocumentBuilder builder = new DocumentBuilder();

	// Pon el texto en negrita.
	builder.Font.Bold = true;
	builder.Writeln("This text will be Bold");  
```

¡Felicidades! Ahora ha aprendido a poner texto en negrita con Aspose.Words para .NET.


