---
title: Enlace
linktitle: Enlace
second_title: API de procesamiento de documentos de Aspose.Words
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


### Preguntas frecuentes

#### P: ¿Cómo puedo vincular a una URL en Aspose.Words?

 R: Para vincular a una dirección URL en Aspose.Words, puede usar el`<a>` etiqueta con el`href` atributo que contiene la dirección URL. Por ejemplo, puedes usar`<a href="https://www.aspose.com">Click Here</a>` para hacer un hipervínculo a la URL "https://www.example.com" con el texto para mostrar "Haga clic aquí".

#### P: ¿Es posible vincular a un marcador interno en Aspose.Words?

 R: Sí, es posible vincular a un marcador interno en Aspose.Words. Puedes usar el`<a>` etiqueta con el`href` atributo que contiene el nombre del marcador precedido por un hash (#). Por ejemplo,`<a href="#bookmark1">Go to bookmark 1</a>` vinculará al marcador denominado "marcador1" en el documento.

#### P: ¿Cómo puedo personalizar el texto de visualización de un enlace en Aspose.Words?

R: Para personalizar el texto de visualización de un enlace en Aspose.Words, puede modificar el contenido entre el`<a>` etiquetas Por ejemplo,`<a href="https://www.aspose.com">Click here</a>` mostrará el texto "Haga clic aquí" como un hipervínculo.

#### P: ¿Puedo especificar un objetivo para un enlace en Aspose.Words?

 R: Sí, puede especificar un objetivo para un enlace en Aspose.Words usando el`target` atributo de la`<a>` etiqueta. Por ejemplo,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` abrirá el enlace en una nueva ventana o pestaña.