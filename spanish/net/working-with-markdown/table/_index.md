---
title: Mesa
linktitle: Mesa
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear una tabla con Aspose.Words para .NET Guía paso a paso.
type: docs
weight: 10
url: /es/net/working-with-markdown/table/
---


En este ejemplo, lo guiaremos a través de cómo crear una tabla usando Aspose.Words para .NET. Una tabla es una estructura de datos que organiza la información en filas y columnas.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Paso 2: Agregar celdas y datos

 Agregaremos celdas y datos a nuestra tabla usando el`InsertCell` método y el`Writeln` método del generador de documentos.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Ejemplo de código fuente para crear una tabla con Aspose.Words para .NET

```csharp
	// Use un generador de documentos para agregar contenido al documento.
	DocumentBuilder builder = new DocumentBuilder();

	// Agrega la primera fila.
	builder.InsertCell();
	builder.Writeln("a");
	builder.InsertCell();
	builder.Writeln("b");

	// Agrega la segunda fila.
	builder.InsertCell();
	builder.Writeln("c");
	builder.InsertCell();
	builder.Writeln("d");
            
```

¡Felicidades! Ahora ha aprendido a crear una tabla con Aspose.Words para .NET.
