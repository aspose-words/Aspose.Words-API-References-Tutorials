---
title: Enlace
linktitle: Enlace
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar enlaces con Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/working-with-markdown/link/
---

En este ejemplo, le explicaremos cómo utilizar la función de enlaces con Aspose.Words para .NET. Los enlaces se utilizan para crear referencias en las que se puede hacer clic a sitios web u otros documentos.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: insertar un enlace

 Podemos insertar un enlace usando el`InsertHyperlink` método del generador de documentos. Necesitamos especificar el texto del enlace, aquí "Aspose", así como la URL de destino.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", falso);
```

### Código fuente de ejemplo para enlaces con Aspose.Words para .NET


```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Insertar el link.
builder.InsertHyperlink("Aspose", "https://www.aspose.com", falso);
```
¡Enhorabuena! Ahora ha aprendido a utilizar la función de enlaces con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo puedo vincular a una URL en Aspose.Words?

 R: Para vincular a una dirección URL en Aspose.Words, puede utilizar el`<a>` etiqueta con el`href` atributo que contiene la dirección URL. Por ejemplo, puedes usar`<a href="https://www.aspose.com">Click Here</a>` para crear un hipervínculo a la URL "https://www.example.com" con el texto mostrado "Haga clic aquí".

#### P: ¿Es posible vincular a un marcador interno en Aspose.Words?

 R: Sí, es posible vincular a un marcador interno en Aspose.Words. Puedes usar el`<a>` etiqueta con el`href` atributo que contiene el nombre del marcador precedido por un hash (#). Por ejemplo,`<a href="#bookmark1">Go to bookmark 1</a>` se vinculará al marcador denominado "bookmark1" en el documento.

#### P: ¿Cómo puedo personalizar el texto que se muestra de un enlace en Aspose.Words?

 R: Para personalizar el texto que se muestra de un enlace en Aspose.Words, puede modificar el contenido entre los`<a>` etiquetas. Por ejemplo,`<a href="https://www.aspose.com">Click here</a>` mostrará el texto "Haga clic aquí" como hipervínculo.

#### P: ¿Puedo especificar un destino para un enlace en Aspose.Words?

R: Sí, puede especificar un destino para un enlace en Aspose.Words usando el`target` atributo de la`<a>` etiqueta. Por ejemplo,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` abrirá el enlace en una nueva ventana o pestaña.