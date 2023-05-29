---
title: Por rango de página
linktitle: Por rango de página
second_title: Referencia de API de Aspose.Words para .NET
description: Extraiga fácilmente por rango de páginas de un documento de Word utilizando Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/split-document/by-page-range/
---

## Introducción
En este tutorial, lo guiaremos paso a paso para comprender y utilizar la funcionalidad "Por rango de páginas" de Aspose.Words para .NET. Esta función le permite extraer una parte específica de un documento de Word grande utilizando un rango de páginas determinado. Le proporcionaremos el código fuente completo y los formatos de salida de Markdown para que sea más fácil de entender y usar más adelante.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente en su lugar:

1. Aspose.Words para .NET instalado en su máquina de desarrollo.
2. Un archivo de Word grande del que desea extraer una parte específica.

Ahora que hemos cubierto los requisitos, podemos pasar a los pasos para usar la función Por rango de páginas.

## Paso 1: inicialización y carga del documento
Una vez que haya configurado su entorno de desarrollo, debe inicializar y cargar el documento de Word del que desea extraer una parte específica. Aquí está el código a utilizar:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Name_of_large_document.docx");
```

Asegúrese de reemplazar "YOUR_DOCUMENTS_DIRECTORY" con la ruta real a su directorio de documentos y "Name_of_large_document.docx" con el nombre de su gran archivo de Word.

## Paso 2: Extrayendo la parte del documento
 Ahora que hemos cargado el documento, podemos extraer la parte específica usando el`ExtractPages` función con el intervalo de páginas deseado. Aquí está cómo hacerlo:

```csharp
Document extractedPages = doc.ExtractPages(3, 6);
```

En este ejemplo, extraemos las páginas 3-6 del documento original. Puede ajustar los números de página según sus necesidades.

## Paso 3: Guarde la parte extraída
Una vez hemos extraído las páginas deseadas, podemos guardarlas en un nuevo documento de Word. Así es cómo:

```csharp
extractedPages.Save(dataDir + "Document_Extraits.ParRangeDePages.docx");
```

Asegúrese de reemplazar "Document_Extraits.ParPlageDePages.docx" con el nombre deseado para su archivo de salida.

### Ejemplo de código fuente para Por rango de páginas usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

// Obtener parte del documento.
Document extractedPages = doc.ExtractPages(3, 6);
extractedPages.Save(dataDir + "SplitDocument.ByPageRange.docx");
```

## Conclusión
¡Felicidades! Ha aprendido a utilizar "Por rango de páginas" de Aspose.Words para .NET. Ahora puede extraer fácilmente partes específicas de un documento de Word grande utilizando un rango de páginas determinado. Siéntase libre de experimentar más con las otras potentes funciones de Aspose. .Palabras para satisfacer sus necesidades específicas.

