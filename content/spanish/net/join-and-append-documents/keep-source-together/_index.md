---
title: Mantenga la fuente unida
linktitle: Mantenga la fuente unida
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a fusionar documentos de Word utilizando Aspose.Words para .NET conservando el formato. Esta guía completa cubre todo, desde la configuración hasta la ejecución.
type: docs
weight: 10
url: /es/net/join-and-append-documents/keep-source-together/
---
## Introducción

En la era digital actual, manipular documentos de Word mediante programación es esencial en diversas industrias. Aspose.Words para .NET permite a los desarrolladores automatizar las tareas de manejo de documentos de manera eficiente. Esta guía completa lo guiará a través del proceso de fusionar documentos mientras conserva el formato fuente usando Aspose.Words para .NET.

## Requisitos previos

Antes de profundizar en la fusión de documentos con Aspose.Words para .NET, asegúrese de tener lo siguiente:

- Visual Studio: Entorno de desarrollo integrado (IDE) para desarrollo .NET.
- Aspose.Words para .NET: instalado y configurado en su entorno de desarrollo.
- Familiaridad con C#: comprensión básica del lenguaje de programación C#.

## Importar espacios de nombres

Para comenzar, importe los espacios de nombres necesarios:

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Paso 1: cargar documentos

 En primer lugar, cargue los documentos de origen y destino en Aspose.Words`Document` objetos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR_DOCUMENT_DIRECTORY/";

// Cargar documentos de origen y destino
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Paso 2: establecer el inicio de la sección

Configure el inicio de la sección para garantizar que el contenido del documento de origen fluya continuamente después del documento de destino.

```csharp
// Configure el documento de origen para que aparezca inmediatamente después del contenido del documento de destino.
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Paso 3: mantenga los párrafos juntos

Para mantener la integridad del formato, marque cada párrafo en el documento fuente para permanecer en el siguiente párrafo.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Paso 4: adjuntar documentos

 Fusionar los documentos usando el`AppendDocument` método, asegurando conservar el formato del documento fuente.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: guardar el documento combinado

Finalmente, guarde el documento combinado en la ubicación deseada.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

## Conclusión

En conclusión, Aspose.Words para .NET simplifica la tarea de fusionar documentos de Word conservando el formato original sin problemas. Esta capacidad es crucial para aplicaciones que requieren procesamiento automatizado de documentos.

## Preguntas frecuentes

### ¿Puede Aspose.Words para .NET fusionar documentos de diferentes formatos?
Sí, puede fusionar documentos independientemente de su formato, manteniendo el formato original.

### ¿Aspose.Words para .NET admite la combinación de documentos grandes de manera eficiente?
Por supuesto, maneja documentos grandes con un rendimiento óptimo.

### ¿Existe una versión de prueba disponible para Aspose.Words para .NET?
 Sí, puedes descargar una prueba gratuita.[aquí](https://releases.aspose.com/).

### ¿Cómo puedo obtener soporte técnico para Aspose.Words para .NET?
 El soporte técnico está disponible a través del[Foro Aspose.Words](https://forum.aspose.com/c/words/8).

### ¿Puedo comprar una licencia temporal de Aspose.Words para .NET?
 Sí, puedes adquirir una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/).