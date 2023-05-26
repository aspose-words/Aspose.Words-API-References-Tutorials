---
title: tachado
linktitle: tachado
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a aplicar el estilo de texto tachado con la guía paso a paso de Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/strikethrough/
---


En este ejemplo, lo guiaremos a través de cómo aplicar el estilo de texto tachado usando Aspose.Words para .NET. El texto tachado se utiliza para indicar que el texto se eliminó o ya no es válido.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: aplica el estilo de texto tachado

 Habilitaremos el estilo de texto tachado configurando el`StrikeThrough` propiedad de la`Font` oponerse a`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Paso 3: Agrega texto tachado

 Ahora podemos agregar texto tachado usando el generador de documentos`Writeln` método.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Código fuente de ejemplo para texto tachado con Aspose.Words para .NET

```csharp
	// Use un generador de documentos para agregar contenido al documento.
	DocumentBuilder builder = new DocumentBuilder();

	// Haz el texto tachado.
	builder.Font.StrikeThrough = true;
	builder.Writeln("This text will be StrikeThrough");
            
```

¡Felicidades! Ahora ha aprendido a aplicar el estilo de texto tachado con Aspose.Words para .NET.
