---
title: Separar palabras de idiomas con guiones
linktitle: Separar palabras de idiomas con guiones
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a dividir palabras en diferentes idiomas en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-hyphenation/hyphenate-words-of-languages/
---

En este tutorial paso a paso, lo guiaremos sobre cómo separar palabras en diferentes idiomas en documentos de Word usando Aspose.Words para .NET. Explicaremos el código fuente C# proporcionado y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo has hecho, descarga e instala la biblioteca desde el sitio oficial.

## Paso 1: Inicializar el objeto del documento

 Primero, inicialice el`Document` objeto especificando la ruta a su documento fuente que contiene texto en diferentes idiomas:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Paso 2: Guardar diccionarios de separación de palabras

A continuación, guarde los diccionarios de separación de palabras para los diferentes idiomas que desee procesar. En este ejemplo, registramos diccionarios de inglés americano y alemán suizo:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Asegúrese de tener los archivos de diccionario adecuados en su directorio de datos.

## Paso 3: Procesar palabras mediante separación de palabras

Ahora puede utilizar funciones de separación de palabras para procesar palabras en diferentes idiomas. Puedes utilizar diferentes métodos de`Document` o`DocumentBuilder` dependiendo de sus necesidades específicas.

```csharp
// Ejemplo: uso del método Hyphenate de DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Paso 4: guarde el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Entonces ! Ha procesado con éxito palabras separándolas con guiones en diferentes idiomas en un documento de Word utilizando Aspose.Words para .NET.

### Código fuente de muestra para separación de palabras usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Siéntase libre de utilizar este código en sus propios proyectos y modificarlo para adaptarlo a sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo puedo silabizar una palabra en un idioma específico con Aspose.Words?

 R: Para silabizar una palabra en un idioma específico con Aspose.Words, puede usar el`Hyphenation` clase y el`Hyphenate()` método. Crear una instancia del`Hyphenation` clase especificando el idioma deseado, luego llame al`Hyphenate()` Método que pasa la palabra a silabizar como argumento. Esto le dará las sílabas de la palabra en el idioma especificado.

#### P: ¿Qué códigos de idioma debo usar para especificar el idioma de silabización en Aspose.Words?

R: Para especificar el idioma de silabización en Aspose.Words, debe utilizar los códigos de idioma apropiados. Por ejemplo, puede utilizar "en" para inglés, "fr" para francés, "es" para español, "de" para alemán, etc. Consulte la documentación de Aspose.Words para obtener una lista completa de los códigos de idioma admitidos.

#### P: ¿La silabización funciona para todos los idiomas en Aspose.Words?

R: La silabización en Aspose.Words depende de las reglas de silabización específicas del idioma. Aunque Aspose.Words admite una amplia gama de idiomas, es posible que algunos idiomas no sean compatibles o que la silabización no esté disponible para ellos. Consulte la documentación de Aspose.Words para descubrir qué idiomas son compatibles con la silabización.