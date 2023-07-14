---
title: Exportar estructura de documento de Word a documento PDF
linktitle: Exportar estructura de documento de Word a documento PDF
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para exportar la estructura de un documento de Word a un documento PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/export-document-structure/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función Exportar estructura de documento de Word a documento PDF con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo exportar la estructura de un documento y generar un PDF con la estructura del documento visible.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Paragraphs.docx" y se encuentra en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Paso 3: Configure las opciones de guardar como PDF

 Para exportar la estructura del documento y hacer que la estructura sea visible en el panel de navegación "Contenido" de Adobe Acrobat Pro mientras se edita el archivo PDF, debemos configurar el`PdfSaveOptions` objeto con el`ExportDocumentStructure` propiedad establecida en`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Paso 4: Guarde el documento como PDF con la estructura del documento

Finalmente, podemos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Eso es todo ! Exportó con éxito una estructura de documento y generó un PDF con la estructura del documento visible usando Aspose.Words para .NET.

### Ejemplo de código fuente para exportar la estructura del documento con Aspose.Words para .NET


```csharp

            // La ruta al directorio de documentos.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // El tamaño del archivo aumentará y la estructura será visible en el panel de navegación "Contenido".
            // de Adobe Acrobat Pro, mientras edita el .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Conclusión

En este tutorial, hemos explicado cómo exportar la estructura de un documento de Word a un documento PDF utilizando Aspose.Words para .NET. Siguiendo los pasos descritos, puede generar fácilmente un PDF con la estructura de su documento visible, lo que facilita la navegación y la búsqueda en el documento. Utilice las funciones de Aspose.Words para .NET para exportar la estructura de sus documentos de Word y crear archivos PDF bien estructurados.

### Preguntas frecuentes

#### P: ¿Qué es exportar la estructura de un documento de Word a un documento PDF?
R: Exportar la estructura de un documento de Word a un documento PDF crea un PDF con una estructura de documento visible. La estructura del documento generalmente incluye cosas como encabezados, secciones, párrafos y otros elementos estructurados del documento. Esta estructura puede ser útil para navegar y buscar en el documento PDF.

#### P: ¿Cómo puedo exportar la estructura de un documento de Word a un documento PDF utilizando Aspose.Words para .NET?
R: Para exportar la estructura de un documento de Word a un documento PDF utilizando Aspose.Words para .NET, siga estos pasos:

 Crear una instancia de la`Document` class especificando la ruta al documento de Word.

 Crear una instancia de la`PdfSaveOptions`clase y establecer el`ExportDocumentStructure` propiedad a`true`. Esto exportará la estructura del documento y la hará visible en el panel de navegación "Contenido" de Adobe Acrobat Pro al editar el archivo PDF.

 Utilizar el`Save` metodo de la`Document`class para guardar el documento en formato PDF especificando las opciones de guardado.

#### P: ¿Cómo puedo ver la estructura de un documento PDF con Adobe Acrobat Pro?
R: Para ver la estructura de un documento PDF con Adobe Acrobat Pro, siga estos pasos:

Abra el documento PDF en Adobe Acrobat Pro.

En la barra de navegación izquierda, haga clic en el icono "Contenido" para mostrar el panel de navegación "Contenido".

En el panel de navegación "Contenido", verá la estructura del documento con encabezados, secciones y otros elementos estructurados.