---
title: Mantener la numeración de fuentes
linktitle: Mantener la numeración de fuentes
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a importar documentos conservando el formato con Aspose.Words para .NET. Guía paso a paso con ejemplos de código.
type: docs
weight: 10
url: /es/net/join-and-append-documents/keep-source-numbering/
---
## Introducción

 Al trabajar con Aspose.Words para .NET, la importación de documentos de una fuente a otra conservando el formato se puede gestionar de manera eficiente utilizando el`NodeImporter` Clase. Este tutorial le guiará a través del proceso paso a paso.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:
- Visual Studio instalado en su máquina.
-  Aspose.Words para .NET está instalado. Si no lo está, descárguelo desde[aquí](https://releases.aspose.com/words/net/).
- Conocimientos básicos de programación C# y .NET.

## Importar espacios de nombres

Primero, incluya los espacios de nombres necesarios en su proyecto:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## Paso 1: Configura tu proyecto

Comience creando un nuevo proyecto C# en Visual Studio e instale Aspose.Words a través del Administrador de paquetes NuGet.

## Paso 2: Inicializar documentos
Crear instancias de la fuente (`srcDoc`) y destino (`dstDoc`) documentos.

```csharp
// Ruta al directorio de su documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: Configurar las opciones de importación
Configure las opciones de importación para mantener el formato de origen, incluidos los párrafos numerados.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Paso 4: Importar párrafos
Iterar a través de los párrafos en el documento de origen e importarlos al documento de destino.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Paso 5: Guardar el documento
Guarde el documento fusionado en la ubicación deseada.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Conclusión

 En conclusión, usar Aspose.Words para .NET para importar documentos conservando el formato es sencillo.`NodeImporter` clase. Este método garantiza que sus documentos mantengan su apariencia y estructura originales sin problemas.

## Preguntas frecuentes

### ¿Puedo importar documentos con diferentes estilos de formato?
 Sí, el`NodeImporter` La clase admite la importación de documentos con distintos estilos de formato.

### ¿Qué pasa si mis documentos contienen tablas e imágenes complejas?
Aspose.Words para .NET maneja estructuras complejas como tablas e imágenes durante las operaciones de importación.

### ¿Aspose.Words es compatible con todas las versiones de .NET?
Aspose.Words admite las versiones .NET Framework y .NET Core para una integración perfecta.

### ¿Cómo puedo gestionar errores durante la importación de documentos?
Utilice bloques try-catch para manejar excepciones que puedan ocurrir durante el proceso de importación.

### ¿Dónde puedo encontrar documentación más detallada sobre Aspose.Words para .NET?
 Visita el[documentación](https://reference.aspose.com/words/net/)para guías completas y referencias API.
