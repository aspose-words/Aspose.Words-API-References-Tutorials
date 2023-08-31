---
title: Establecer opciones de esquema en un documento PDF
linktitle: Establecer opciones de esquema en un documento PDF
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para configurar opciones de esquema en un documento PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/set-outline-options/
---

Este artículo proporciona una guía paso a paso sobre cómo utilizar la función establecer opciones de esquema para el tamaño de metarchivo con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo configurar opciones de esquema en un documento y generar un PDF con las opciones de esquema correspondientes.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Rendering.docx" y está ubicado en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: Configure las opciones de guardar como PDF con las opciones del plan

 Para configurar las opciones de esquema en el PDF generado, necesitamos configurar el`PdfSaveOptions` objeto. Podemos establecer el número de niveles de esquema de encabezado (`HeadingsOutlineLevels`) y el número de niveles de esquema ampliados (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Paso 4: guarde el documento como PDF con opciones de esquema

Finalmente podremos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Eso es todo ! Ha configurado correctamente las opciones de esquema en un documento y ha generado un PDF con las opciones de esquema correspondientes utilizando Aspose.Words para .NET.

### Código fuente de ejemplo para configurar las opciones del plan al tamaño de metarchivo con Aspose.Words para .NET


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Conclusión

En este tutorial, explicamos cómo configurar opciones de esquema en un documento PDF usando Aspose.Words para .NET. Siguiendo los pasos descritos, puede especificar fácilmente los niveles de encabezado y esquema en su documento y generar un archivo PDF con las opciones de esquema correspondientes. Disfrute de los beneficios de la opción de esquema para mejorar la estructura y la navegación en sus documentos PDF utilizando Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cuál es la opción de esquema en un documento PDF?
R: La opción de esquema en un documento PDF se refiere a la estructura jerárquica del contenido del documento. Le permite crear una tabla de contenido interactiva y facilita la navegación en el documento. Las opciones de esquema determinan los niveles de título y subtítulo que se incluirán en el esquema y el nivel de detalle que se mostrará en el esquema generado.

#### P: ¿Cómo puedo configurar opciones de esquema en un documento PDF usando Aspose.Words para .NET?
R: Para configurar opciones de esquema en un documento PDF usando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENT DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento que desea convertir a PDF usando el`Document` clase y especifique la ruta al documento en el directorio de documentos especificado.

 Configure las opciones de guardar como PDF creando una instancia del`PdfSaveOptions` clase y usando el`OutlineOptions` propiedad para establecer las opciones de esquema. Puede especificar el número de niveles de encabezado para incluir en el esquema usando el`HeadingsOutlineLevels` propiedad y el número de niveles de esquema ampliados utilizando el`ExpandedOutlineLevels` propiedad.

 Guarde el documento en formato PDF utilizando el`Save` método de la`Document`clase que especifica la ruta y las opciones de guardado.

#### P: ¿Para qué sirve la opción de plan en un documento PDF?
R: La opción de esquema en un documento PDF le permite crear una estructura jerárquica del contenido, lo que facilita la navegación por el documento y el acceso a diferentes secciones. Esto permite a los usuarios saltar rápidamente a partes específicas del documento haciendo clic en las entradas de la tabla de contenido o del esquema. La opción de esquema también mejora la experiencia de lectura al proporcionar una descripción general de la estructura general del documento.
