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

//Insertar hipervínculo.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


¡Felicidades! Ahora ha aprendido a usar la función "Autolink" con Aspose.Words para .NET.

