---
title: Enlace
linktitle: Enlace
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar enlaces con Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/working-with-markdown/link/
---

En este ejemplo, lo guiaremos a través de cómo usar la función de enlaces con Aspose.Words para .NET. Los enlaces se utilizan para crear referencias en las que se puede hacer clic a sitios web u otros documentos.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: Insertar un enlace

 Podemos insertar un enlace usando el`Insertlink` método del generador de documentos. Necesitamos especificar el texto del enlace, aquí "Aspose", así como la URL de destino.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", falso);
```

### Ejemplo de código fuente para enlaces con Aspose.Words para .NET


```csharp
	// Use un generador de documentos para agregar contenido al documento.
	DocumentBuilder builder = new DocumentBuilder();

	// Insertar el link.
	builder.Insertlink("Aspose", "https://www.aspose.com", falso);
            
```
¡Felicidades! Ahora ha aprendido a usar la función de enlaces con Aspose.Words para .NET.

