---
title: Tachado
linktitle: Tachado
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo aplicar formato tachado al texto usando Aspose.Words para .NET con nuestra guía paso a paso. Mejore sus habilidades de procesamiento de documentos.
type: docs
weight: 10
url: /es/net/working-with-markdown/strikethrough/
---
## Introducción

Bienvenido a esta guía detallada sobre cómo aplicar formato tachado al texto usando Aspose.Words para .NET. Si buscas mejorar tus habilidades de procesamiento de documentos y agregar un toque único a tu texto, estás en el lugar correcto. ¡Vamos a sumergirnos!

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

-  Aspose.Words para .NET: Descárgalo[aquí](https://releases.aspose.com/words/net/).
- .NET Framework: asegúrese de tener .NET Framework instalado en su sistema.
- Entorno de desarrollo: un IDE como Visual Studio.
- Conocimientos básicos de C#: es necesaria estar familiarizado con la programación en C#.

## Importar espacios de nombres

Para comenzar, deberá importar los espacios de nombres necesarios. Estos son esenciales para acceder a la biblioteca Aspose.Words y sus funciones.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Paso 1: Inicialice DocumentBuilder

 El`DocumentBuilder` class es una poderosa herramienta en Aspose.Words que le permite agregar contenido a su documento con facilidad.

```csharp
// Inicialice un DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: establecer la propiedad tachada

Ahora, apliquemos la propiedad de tachado a nuestro texto. Esto implica establecer el`StrikeThrough` propiedad de la`Font` oponerse a`true`.

```csharp
// Haz que el texto esté tachado.
builder.Font.StrikeThrough = true;
```

## Paso 3: escribe texto tachado

 Con la propiedad de tachado configurada, ahora podemos agregar nuestro texto. El`Writeln` El método agregará el texto al documento.

```csharp
// Escribe texto con tachado.
builder.Writeln("This text will be StrikeThrough");
```

## Conclusión

¡Y ahí lo tienes! Ha agregado con éxito formato tachado a su texto usando Aspose.Words para .NET. Esta poderosa biblioteca abre un mundo de posibilidades para el procesamiento y personalización de documentos. Ya sea que esté creando informes, cartas o cualquier otro tipo de documento, dominar estas funciones sin duda mejorará su productividad y la calidad de sus resultados.

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una potente biblioteca de procesamiento de documentos que permite a los desarrolladores crear, manipular y convertir documentos de Word mediante programación.

### ¿Puedo utilizar Aspose.Words para .NET en un proyecto comercial?
 Sí, puede utilizar Aspose.Words para .NET en proyectos comerciales. Para opciones de compra, visite el[comprar pagina](https://purchase.aspose.com/buy).

### ¿Hay una prueba gratuita disponible para Aspose.Words para .NET?
 Sí, puedes descargar una prueba gratuita.[aquí](https://releases.aspose.com/).

### ¿Cómo obtengo soporte para Aspose.Words para .NET?
Puede obtener apoyo de la comunidad de Aspose y de expertos en el[foro de soporte](https://forum.aspose.com/c/words/8).

### ¿Puedo aplicar otras opciones de formato de texto usando Aspose.Words para .NET?
¡Absolutamente! Aspose.Words para .NET admite una amplia gama de opciones de formato de texto que incluyen negrita, cursiva, subrayado y más.