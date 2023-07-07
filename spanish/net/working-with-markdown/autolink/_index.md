---
title: Enlace automático
linktitle: Enlace automático
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar enlaces automáticos con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/autolink/
---

En este ejemplo, explicaremos cómo usar la función "Autolink" con Aspose.Words para .NET. Esta característica le permite insertar hipervínculos en su documento automáticamente.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: Insertar un hipervínculo

 Podemos insertar un hipervínculo usando el`InsertHyperlink` método del generador de documentos. Especificamos la URL y el texto a mostrar para el enlace.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
```

## Paso 3: Insertar una dirección de correo electrónico como enlace

También podemos insertar una dirección de correo electrónico como enlace usando el prefijo "mailto:". Esto permitirá a los usuarios hacer clic en el enlace para abrir su cliente de correo electrónico predeterminado.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Paso 4: Guardar el documento

Finalmente, podemos guardar el documento en el formato deseado.

### Código fuente de ejemplo para Autolink usando Aspose.Words para .NET


```csharp
// Use un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Insertar hipervínculo.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


¡Felicidades! Ahora ha aprendido a usar la función "Autolink" con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo puedo crear un enlace automático a una dirección URL en Aspose.Words?

 R: Para crear un enlace automático a una dirección URL en Aspose.Words, puede usar el`<a>` etiqueta con el`href` atributo que contiene la dirección URL. Por ejemplo, puedes usar`<a href="https://www.aspose.com">https://www.aspose.com</a>` para vincular automáticamente a "https: //www.aspose.com".

#### P: ¿Es posible personalizar el texto de visualización de un enlace automático en Aspose.Words?

 R: Sí, puede personalizar el texto de visualización de un enlace automático en Aspose.Words. En lugar de usar la dirección URL como texto para mostrar, puede usar cualquier otro texto reemplazando el contenido entre el`<a>` etiquetas Por ejemplo, puedes usar`<a href="https://www.aspose.com">Click here</a>` para mostrar el texto "Haga clic aquí" como un enlace automático.

#### P: ¿Cómo puedo agregar atributos adicionales a un enlace automático en Aspose.Words?

R: Para agregar atributos adicionales a un enlace automático en Aspose.Words, puede usar atributos HTML adicionales dentro del`<a>` etiqueta. Por ejemplo, puedes usar`<a href="https://www.aspose.com" target="_blank">Link</a>` para abrir el enlace en una nueva ventana o pestaña usando el` attribute target="_blank"`.