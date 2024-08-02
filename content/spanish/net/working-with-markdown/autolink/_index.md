---
title: Enlace automático
linktitle: Enlace automático
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo insertar un enlace automático con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/autolink/
---

En este ejemplo, explicaremos cómo utilizar la función "Autolink" con Aspose.Words para .NET. Esta función le permite insertar hipervínculos en su documento automáticamente.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: insertar un hipervínculo

 Podemos insertar un hipervínculo usando el`InsertHyperlink` método del generador de documentos. Especificamos la URL y el texto a mostrar para el enlace.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
```

## Paso 3: Insertar una dirección de correo electrónico como enlace

También podemos insertar una dirección de correo electrónico como enlace utilizando el prefijo "mailto:". Esto permitirá a los usuarios hacer clic en el enlace para abrir su cliente de correo electrónico predeterminado.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Paso 4: guardar el documento

Finalmente, podremos guardar el documento en el formato deseado.

### Ejemplo de código fuente para Autolink usando Aspose.Words para .NET


```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Insertar hipervínculo.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


¡Enhorabuena! Ahora ha aprendido a utilizar la función "Enlace automático" con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo puedo crear un enlace automático a una dirección URL en Aspose.Words?

 R: Para crear un enlace automático a una dirección URL en Aspose.Words, puede utilizar el`<a>` etiqueta con el`href` atributo que contiene la dirección URL. Por ejemplo, puedes usar`<a href="https://www.aspose.com">https://www.aspose.com</a>` para vincularse automáticamente a "https://www.aspose.com".

#### P: ¿Es posible personalizar el texto que se muestra de un enlace automático en Aspose.Words?

 R: Sí, puede personalizar el texto que se muestra de un enlace automático en Aspose.Words. En lugar de utilizar la dirección URL como texto para mostrar, puede utilizar cualquier otro texto reemplazando el contenido entre los`<a>` etiquetas. Por ejemplo, puedes usar`<a href="https://www.aspose.com">Click here</a>`para mostrar el texto "Haga clic aquí" como enlace automático.

#### P: ¿Cómo puedo agregar atributos adicionales a un enlace automático en Aspose.Words?

 R: Para agregar atributos adicionales a un enlace automático en Aspose.Words, puede usar atributos HTML adicionales dentro del`<a>` etiqueta. Por ejemplo, puedes usar`<a href="https://www.aspose.com" target="_blank">Link</a>` para abrir el enlace en una nueva ventana o pestaña usando el` attribute target="_blank"`.