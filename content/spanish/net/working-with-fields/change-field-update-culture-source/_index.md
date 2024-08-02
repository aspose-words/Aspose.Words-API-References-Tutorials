---
title: Cambiar fuente de cultura de actualización de campo
linktitle: Cambiar fuente de cultura de actualización de campo
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo cambiar la fuente cultural de actualización de campos en Aspose.Words para .NET con esta guía. Controle fácilmente el formato de fecha basado en diferentes culturas.
type: docs
weight: 10
url: /es/net/working-with-fields/change-field-update-culture-source/
---
## Introducción

En este tutorial, nos sumergiremos en el mundo de Aspose.Words para .NET y exploraremos cómo cambiar la fuente cultural de actualización de campo. Si está trabajando con documentos de Word que incluyen campos de fecha y necesita controlar cómo se formatean estas fechas según las diferentes culturas, esta guía es para usted. Repasemos el proceso paso a paso, asegurándonos de que comprenda cada concepto y pueda aplicarlo de manera efectiva en sus proyectos.

## Requisitos previos

Antes de pasar al código, asegúrese de tener lo siguiente:

-  Aspose.Words para .NET: puedes descargarlo desde[aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: cualquier IDE compatible con .NET (por ejemplo, Visual Studio).
- Conocimientos básicos de C#: este tutorial asume que tienes un conocimiento fundamental de la programación en C#.

## Importar espacios de nombres

Primero, importemos los espacios de nombres necesarios para nuestro proyecto. Esto asegurará que tengamos acceso a todas las clases y métodos requeridos proporcionados por Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Ahora, dividamos el ejemplo en varios pasos para ayudarlo a comprender cómo cambiar la fuente cultural de actualización del campo en Aspose.Words para .NET.

## Paso 1: Inicializar el documento

 El primer paso es crear una nueva instancia del`Document` clase y un`DocumentBuilder`. Esto sienta las bases para construir y manipular nuestro documento de Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: insertar campos con una configuración regional específica

A continuación, debemos insertar campos en el documento. Para este ejemplo, insertaremos dos campos de fecha. Estableceremos la configuración regional de la fuente en alemán (LocaleId = 1031) para demostrar cómo la cultura afecta el formato de fecha.

```csharp
builder.Font.LocaleId = 1031; // Alemán
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

## Paso 3: Establecer la fuente cultural de actualización de campo

 Para controlar la cultura utilizada al actualizar los campos, configuramos el`FieldUpdateCultureSource` propiedad de la`FieldOptions`clase. Esta propiedad determina si la cultura se toma del código de campo o del documento.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

## Paso 4: ejecutar combinación de correspondencia

Ahora necesitamos ejecutar una combinación de correspondencia para completar los campos con datos reales. En este ejemplo, configuraremos el segundo campo de fecha (`Date2`) al 1 de enero de 2011.

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

## Paso 5: guarde el documento

Finalmente, guardamos el documento en el directorio especificado. Este paso completa el proceso de cambiar la fuente cultural de actualización de campo.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusión

¡Y ahí lo tienes! Ha cambiado con éxito la fuente cultural de actualización de campo en Aspose.Words para .NET. Si sigue estos pasos, puede asegurarse de que sus documentos de Word muestren fechas y otros valores de campo de acuerdo con la configuración cultural especificada. Esto puede resultar particularmente útil al generar documentos para una audiencia internacional.

## Preguntas frecuentes

###  ¿Cuál es el propósito de establecer el`LocaleId`?
 El`LocaleId` especifica la configuración cultural del texto, lo que afecta el formato de las fechas y otros datos sensibles a la configuración regional.

### ¿Puedo utilizar una configuración regional distinta al alemán?
 Sí, puedes configurar el`LocaleId` cualquier identificador local válido. Por ejemplo, 1033 para inglés (Estados Unidos).

###  ¿Qué pasa si no configuro el`FieldUpdateCultureSource` property?
Si esta propiedad no está configurada, se utilizará la configuración cultural predeterminada del documento al actualizar los campos.

### ¿Es posible actualizar campos según la cultura del documento en lugar del código de campo?
 Sí, puedes configurar`FieldUpdateCultureSource` a`FieldUpdateCultureSource.Document` para utilizar la configuración cultural del documento.

### ¿Cómo formato las fechas con un patrón diferente?
 Puede cambiar el patrón de formato de fecha en el`InsertField` método modificando el`\\@` valor del interruptor.