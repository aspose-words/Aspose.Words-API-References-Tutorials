---
title: Obtener separador de estilo de párrafo
linktitle: Obtener separador de estilo de párrafo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a obtener el separador de estilo de párrafo con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/get-paragraph-style-separator/
---

En este tutorial, lo guiaremos a través de cómo usar la función Obtener separador de estilo de párrafo con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: Cargar el documento

Para comenzar, especifique el directorio para sus documentos y cargue el documento en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Paso 2: encontrar separadores de estilo de párrafo

Ahora recorreremos todos los párrafos del documento y comprobaremos si un párrafo es un separador de estilo. Así es cómo:

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### Código fuente de ejemplo para Obtener separador de estilo de párrafo usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Obtener separador de estilo de párrafo con Aspose.Words para .NET:

```csharp

            Document doc = new Document(MyDir + "Document.docx");

            foreach (Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
            {
                if (paragraph.BreakIsStyleSeparator)
                {
                    Console.WriteLine("Separator Found!");
                }
            }
        
```

Con este código podrá encontrar los separadores de estilo de párrafo en un documento usando Aspose.Words para .NET.

