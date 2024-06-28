---
title: Cargar diccionario de separación de palabras para el idioma
linktitle: Cargar diccionario de separación de palabras para el idioma
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a cargar un diccionario de separación de palabras para un idioma específico en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

En este tutorial paso a paso, le mostraremos cómo cargar un diccionario de separación de palabras para un idioma específico en Aspose.Words para .NET. Explicaremos el código fuente C# proporcionado y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo has hecho, descarga e instala la biblioteca desde[Aspose.Releases]https://releases.aspose.com/words/net/.

## Paso 1: cargar el documento

Primero, cargue su documento desde el directorio especificado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Paso 2: cargar el diccionario de separación de palabras

A continuación, abra una secuencia en el archivo del diccionario de separación de palabras y guárdela en el idioma deseado. En este ejemplo, cargamos un diccionario de alemán suizo (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Asegúrese de tener el archivo de diccionario apropiado en su directorio de datos.

## Paso 3: guarde el documento modificado

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Entonces ! Ha cargado correctamente un diccionario de separación de palabras para un idioma específico en Aspose.Words para .NET.

### Código fuente de ejemplo para cargar un diccionario de separación de palabras para un idioma usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Siéntase libre de utilizar este código en sus propios proyectos y modificarlo para adaptarlo a sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo cargar un diccionario de silabización para un idioma específico en Aspose.Words?

 R: Para cargar un diccionario de silabización para un idioma específico en Aspose.Words, puede usar el`Hyphenation` clase y el`LoadDictionary()` método. Crear una instancia del`Hyphenation` clase y llamar al`LoadDictionary()` Método que especifica la ruta al archivo del diccionario de silabización para el idioma deseado. Esto cargará el diccionario de silabización en Aspose.Words.

#### P: ¿Dónde puedo encontrar archivos de diccionario de silabización para diferentes idiomas?

R: Puede encontrar archivos de diccionario de silabización para diferentes idiomas en varios recursos en línea. Estos archivos suelen estar en formato XML o TEX. Puede encontrar diccionarios de silabización de código abierto para diferentes idiomas en sitios web dedicados a proyectos de lingüística o repositorios de código fuente.

#### P: ¿Cómo puedo aplicar el diccionario silábico cargado a un documento en Aspose.Words?

R: Para aplicar el diccionario de silabización cargado a un documento en Aspose.Words, necesita iterar sobre las palabras en el documento y usar el`Hyphenate()` método de la`Hyphenation` clase para conseguir la silabización de las palabras. Luego puede formatear las palabras con sílabas según sea necesario, por ejemplo agregando guiones entre sílabas.

#### P: ¿Qué idiomas se admiten para la silabización en Aspose.Words?

R: Aspose.Words admite la silabización en varios idiomas, incluidos inglés, francés, español, alemán, italiano, holandés, ruso, portugués, sueco, noruego, danés, finlandés, polaco, checo y muchos más. Consulte la documentación de Aspose.Words para obtener la lista completa de idiomas admitidos para la silabización.