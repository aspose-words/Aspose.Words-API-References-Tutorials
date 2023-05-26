---
title: Cargar diccionario de partición de palabras para el idioma
linktitle: Cargar diccionario de partición de palabras para el idioma
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a cargar un diccionario de división de palabras para un idioma específico en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

En este tutorial paso a paso, le mostraremos cómo cargar un diccionario de guiones para un idioma específico en Aspose.Words para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo ha hecho, descargue e instale la biblioteca desde el sitio oficial.

## Paso 1: Cargar el documento

Primero, cargue su documento desde el directorio especificado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Paso 2: Cargar el diccionario de separación silábica

A continuación, abra una secuencia en el archivo del diccionario de separación de palabras y guárdelo para el idioma deseado. En este ejemplo, cargamos un diccionario para alemán suizo (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Asegúrese de tener el archivo de diccionario apropiado en su directorio de datos.

## Paso 3: Guarde el documento modificado

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Entonces ! Ha cargado correctamente un diccionario de división de palabras para un idioma específico en Aspose.Words para .NET.

### Código fuente de ejemplo para la carga del diccionario de partición de palabras para un idioma usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo para satisfacer sus necesidades específicas.