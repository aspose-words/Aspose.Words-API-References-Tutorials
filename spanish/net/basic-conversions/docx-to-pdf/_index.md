---
title: Convertir archivo de Word a PDF
linktitle: Convertir archivo de Word a PDF
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a convertir documentos de Word de Docx a PDF usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-pdf/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento de Word en formato Docx a PDF. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto con la ruta a su documento de origen en formato Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Paso 2: Guardar el documento en formato PDF

 A continuación, guarde el documento en formato PDF llamando al`Save` método en el`Document` objeto y proporcionando la ruta y el nombre de archivo para el documento PDF de salida:

```csharp
doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
```

¡Eso es todo! Ha convertido con éxito un documento de Word en formato Docx a PDF usando Aspose.Words para .NET.

### Código fuente de ejemplo para Docx To Pdf usando Aspose.Words para .NET

```csharp

	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
	
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.

### Preguntas frecuentes sobre la conversión de Word a PDF

#### Q1. ¿Cuáles son los requisitos para realizar la conversión de DOCX a PDF con Aspose.Words para .NET?
Para ejecutar la conversión de DOCX a PDF con Aspose.Words para .NET, necesita:
Aspose.Words para .NET instalado en su máquina
Un archivo DOCX válido para convertir
Una licencia válida para usar Aspose.Words para .NET (o puede usar la versión de prueba gratuita)

#### Q2. ¿Cómo puedo instalar Aspose.Words para .NET?
Puede instalar Aspose.Words para .NET siguiendo estos pasos:

Abra Visual Studio o su entorno de desarrollo preferido.

Cree un nuevo proyecto o abra un proyecto existente.

Haga clic con el botón derecho en el proyecto en el Explorador de soluciones.

Seleccione "Administrar paquetes NuGet" en el menú contextual.

Busque "Aspose.Words" en el cuadro de búsqueda.

Seleccione la última versión de Aspose.Words para .NET.

Haga clic en "Instalar" para agregar la referencia a su proyecto.

#### Q3. ¿Qué otras opciones de conversión están disponibles con Aspose.Words para .NET?
Además de convertir DOCX a PDF, Aspose.Words para .NET admite otras conversiones, como:

DOCX a otros formatos de archivo, como DOC, RTF, HTML, XML, etc.

Convierta archivos PDF a formatos como DOCX, DOC, HTML, etc.

Conversión de archivos EPUB, ODT, OTT, TXT, etc. a otros formatos.


#### Q4. ¿Dónde puedo encontrar más código de muestra y recursos para el procesamiento de textos con Aspose.Words para .NET?
 Puede encontrar más ejemplos de código y recursos en el[Referencia de API de Aspose.Words para .NET](https://reference.aspose.com/words/net/) y[Tutoriales de API de Aspose.Words para .NET](https://reference.aspose.com/tutorials/words/net/). Estos recursos proporcionan guías paso a paso, código de muestra y tutoriales.