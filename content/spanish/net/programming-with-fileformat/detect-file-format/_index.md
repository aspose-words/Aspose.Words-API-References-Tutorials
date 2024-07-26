---
title: Detectar formato de archivo de documento
linktitle: Detectar formato de archivo de documento
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a detectar formatos de archivos de documentos utilizando Aspose.Words para .NET con esta guía completa paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-fileformat/detect-file-format/
---
## Introducción

En el mundo digital actual, gestionar diferentes formatos de documentos de manera eficiente es crucial. Ya sea que maneje Word, PDF, HTML u otros formatos, poder detectar y procesar estos archivos correctamente puede ahorrarle mucho tiempo y esfuerzo. En este tutorial, exploraremos cómo detectar formatos de archivos de documentos usando Aspose.Words para .NET. Esta guía lo guiará a través de todo lo que necesita saber, desde requisitos previos hasta una guía detallada paso a paso.

## Requisitos previos

Antes de profundizar en el código, asegurémonos de que tiene todo lo que necesita:

-  Aspose.Words para .NET: puede descargarlo desde[aquí](https://releases.aspose.com/words/net/) . Asegúrese de tener una licencia válida. Si no, puedes conseguir un[licencia temporal](https://purchase.aspose.com/temporary-license/).
- Visual Studio: cualquier versión reciente funcionará bien.
- .NET Framework: asegúrese de tener instalada la versión correcta.

## Importar espacios de nombres

Para comenzar, necesitarás importar los espacios de nombres necesarios en tu proyecto:

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

Dividamos el ejemplo en varios pasos para que sea más fácil de seguir.

## Paso 1: configurar directorios

Primero, necesitamos configurar directorios donde se ordenarán los archivos según su formato.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Cree los directorios si aún no existen.
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## Paso 2: obtenga la lista de archivos

A continuación, obtendremos una lista de archivos del directorio, excluyendo los documentos dañados.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Paso 3: detectar formatos de archivo

Ahora, recorremos cada archivo y detectamos su formato usando Aspose.Words.

```csharp
foreach (string fileName in fileList)
{
    string nameOnly = Path.GetFileName(fileName);

    Console.Write(nameOnly);

    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

    // Mostrar el tipo de documento
    switch (info.LoadFormat)
    {
        case LoadFormat.Doc:
            Console.WriteLine("\tMicrosoft Word 97-2003 document.");
            break;
        case LoadFormat.Dot:
            Console.WriteLine("\tMicrosoft Word 97-2003 template.");
            break;
        case LoadFormat.Docx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
            break;
        case LoadFormat.Docm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
            break;
        case LoadFormat.Dotx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
            break;
        case LoadFormat.Dotm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
            break;
        case LoadFormat.FlatOpc:
            Console.WriteLine("\tFlat OPC document.");
            break;
        case LoadFormat.Rtf:
            Console.WriteLine("\tRTF format.");
            break;
        case LoadFormat.WordML:
            Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
            break;
        case LoadFormat.Html:
            Console.WriteLine("\tHTML format.");
            break;
        case LoadFormat.Mhtml:
            Console.WriteLine("\tMHTML (Web archive) format.");
            break;
        case LoadFormat.Odt:
            Console.WriteLine("\tOpenDocument Text.");
            break;
        case LoadFormat.Ott:
            Console.WriteLine("\tOpenDocument Text Template.");
            break;
        case LoadFormat.DocPreWord60:
            Console.WriteLine("\tMS Word 6 or Word 95 format.");
            break;
        case LoadFormat.Unknown:
            Console.WriteLine("\tUnknown format.");
            break;
    }

    if (info.IsEncrypted)
    {
        Console.WriteLine("\tAn encrypted document.");
        File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
    }
    else
    {
        switch (info.LoadFormat)
        {
            case LoadFormat.DocPreWord60:
                File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
                break;
            case LoadFormat.Unknown:
                File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
                break;
            default:
                File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
                break;
        }
    }
}
```

## Conclusión

Detectar formatos de archivos de documentos usando Aspose.Words para .NET es un proceso sencillo. Al configurar sus directorios, obtener su lista de archivos y utilizar Aspose.Words para detectar formatos de archivos, puede organizar y administrar sus documentos de manera eficiente. Este enfoque no sólo ahorra tiempo sino que también garantiza el manejo correcto de varios formatos de documentos.

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca para trabajar con documentos de Word mediante programación. Permite a los desarrolladores crear, modificar y convertir documentos en varios formatos.

### ¿Puede Aspose.Words detectar documentos cifrados?
Sí, Aspose.Words puede detectar si un documento está cifrado y usted puede manejar dichos documentos en consecuencia.

### ¿Qué formatos puede detectar Aspose.Words?
Aspose.Words puede detectar una amplia gama de formatos, incluidos DOC, DOCX, RTF, HTML, MHTML, ODT y muchos más.

### ¿Cómo puedo obtener una licencia temporal para Aspose.Words?
 Puede obtener una licencia temporal del[Asponer compra](https://purchase.aspose.com/temporary-license/) página.

### ¿Dónde puedo encontrar la documentación de Aspose.Words?
 La documentación para Aspose.Words se puede encontrar[aquí](https://reference.aspose.com/words/net/).
