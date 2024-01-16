---
title: Dividir documento de Word por encabezados HTML
linktitle: Por encabezados HTML
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para explicar el código fuente C# del documento de Word dividido mediante la función HTML de encabezado de Aspose.Words para .NET
type: docs
weight: 10
url: /es/net/split-document/by-headings-html/
---
En este tutorial, le explicaremos cómo dividir un documento de Word en partes más pequeñas utilizando la función Por encabezado HTML de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y generar documentos HTML separados basados en el encabezado.

## Paso 1: cargar el documento

Para comenzar, especifique el directorio de su documento y cárguelo en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Paso 2: Dividir el documento por Título en formato HTML

Ahora configuraremos las opciones de guardar para dividir el documento en partes más pequeñas según el encabezado en formato HTML. Así es cómo:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Divide el documento en partes más pequeñas, en este caso separándolo por título.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Código fuente de ejemplo para By Headings HTML usando Aspose.Words para .NET

Aquí está el código fuente completo de la función Por encabezado HTML de Aspose.Words para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Divida un documento en partes más pequeñas, en este caso dividido por título.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Con este código, podrá dividir un documento de Word en partes más pequeñas usando Aspose.Words para .NET, según los encabezados. Luego puede generar documentos HTML separados para cada parte.

## Conclusión

 En este tutorial, aprendimos cómo dividir un documento de Word en partes más pequeñas usando la función Por encabezado HTML de Aspose.Words para .NET. Al especificar el`DocumentSplitCriteria` como`HeadingParagraph` en el`HtmlSaveOptions`, pudimos generar documentos HTML separados basados en los encabezados presentes en el documento original.

Dividir un documento por títulos puede resultar útil para organizar y gestionar el contenido, especialmente en documentos grandes con varias secciones. Aspose.Words para .NET proporciona una solución confiable y eficiente para manejar la división de documentos y generar resultados en varios formatos.

No dude en explorar funciones y opciones adicionales proporcionadas por Aspose.Words para .NET para mejorar aún más sus capacidades de procesamiento de documentos y optimizar su flujo de trabajo.

### Preguntas frecuentes

#### ¿Cómo puedo dividir un documento de Word en partes más pequeñas según los títulos usando Aspose.Words para .NET?

 Para dividir un documento de Word según los encabezados, puede utilizar la función Por encabezado HTML de Aspose.Words para .NET. Siga el código fuente proporcionado y configure el`DocumentSplitCriteria` a`HeadingParagraph` en el`HtmlSaveOptions` objeto. Esto dividirá el documento en partes más pequeñas en cada encabezado.

#### ¿En qué formatos puedo dividir el documento de Word?

El código fuente proporcionado demuestra cómo dividir el documento de Word en partes más pequeñas en formato HTML. Sin embargo, Aspose.Words para .NET admite varios formatos de salida, incluidos DOCX, PDF, EPUB y más. Puede modificar el código y especificar el formato de salida deseado en el`HtmlSaveOptions` objetar en consecuencia.

#### ¿Puedo elegir un criterio diferente para dividir el documento?

 Sí, puede elegir un criterio diferente para dividir el documento según sus requisitos. Aspose.Words para .NET proporciona varias opciones de criterios, como`HeadingParagraph`, `Page`, `Section` , y más. Modificar el`DocumentSplitCriteria` propiedad en el`HtmlSaveOptions` objeto para seleccionar los criterios apropiados para la partición.

#### ¿Cómo puedo personalizar el HTML de salida para las partes divididas?

 Aspose.Words para .NET le permite personalizar el HTML de salida para las partes divididas especificando opciones adicionales en el`HtmlSaveOptions` objeto. Puede controlar varios aspectos, como estilos CSS, imágenes, fuentes y más. Consulte la documentación de Aspose.Words para obtener más detalles sobre cómo personalizar la salida HTML.

#### ¿Puedo dividir el documento según varios criterios?

 Sí, puede dividir el documento según varios criterios combinando las opciones de criterios en consecuencia. Por ejemplo, puede dividir el documento por encabezado y página configurando el`DocumentSplitCriteria`propiedad a`HeadingParagraph | Page`. Esto dividirá el documento en cada encabezado y cada página, creando partes más pequeñas según ambos criterios.