---
title: Separar Palabras De Idiomas
linktitle: Separar Palabras De Idiomas
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a separar palabras en diferentes idiomas en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-hyphenation/hyphenate-words-of-languages/
---

En este tutorial paso a paso, lo guiaremos sobre cómo separar palabras en diferentes idiomas en documentos de Word usando Aspose.Words para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo ha hecho, descargue e instale la biblioteca desde el sitio oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto especificando la ruta a su documento de origen que contiene texto en diferentes idiomas:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Paso 2: Guardar diccionarios de separación de sílabas

A continuación, guarde los diccionarios de partición de palabras para los diferentes idiomas que desea procesar. En este ejemplo, registramos diccionarios para inglés americano y alemán suizo:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Asegúrese de tener los archivos de diccionario apropiados en su directorio de datos.

## Paso 3: procesamiento de palabras por separación de sílabas

 Ahora puede usar las funciones de división de palabras para procesar palabras en diferentes idiomas. Puede utilizar diferentes métodos de`Document` o`DocumentBuilder` dependiendo de sus necesidades específicas.

```csharp
// Ejemplo: uso del método de guiones de DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Paso 4: Guarde el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Entonces ! Ha procesado correctamente las palabras al dividirlas en diferentes idiomas en un documento de Word utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para separación de palabras usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo para satisfacer sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo puedo silabear una palabra en un idioma específico con Aspose.Words?

 R: Para silabear una palabra en un idioma específico con Aspose.Words, puede usar el`Hyphenation` clase y el`Hyphenate()` método. Crear una instancia de la`Hyphenation` clase especificando el idioma deseado, luego llame al`Hyphenate()` método que pasa la palabra a silabear como un argumento. Esto le dará las sílabas de la palabra en el idioma especificado.

#### P: ¿Qué códigos de idioma debo usar para especificar el idioma de silabeo en Aspose.Words?

R: Para especificar el idioma de silabeo en Aspose.Words, debe usar los códigos de idioma apropiados. Por ejemplo, puede usar "en" para inglés, "fr" para francés, "es" para español, "de" para alemán, etc. Consulte la documentación de Aspose.Words para obtener una lista completa de los códigos de idioma admitidos.

#### P: ¿Funciona el silabeo para todos los idiomas en Aspose.Words?

R: El silabeo en Aspose.Words depende de las reglas de silabeo específicas del idioma. Aunque Aspose.Words es compatible con una amplia gama de idiomas, es posible que algunos idiomas no sean compatibles o que el silabeo no esté disponible para ellos. Consulte la documentación de Aspose.Words para averiguar qué idiomas son compatibles con el silabismo.