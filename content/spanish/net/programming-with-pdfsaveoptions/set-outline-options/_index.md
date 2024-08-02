---
title: Establecer opciones de esquema en un documento PDF
linktitle: Establecer opciones de esquema en un documento PDF
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar opciones de esquema en un documento PDF usando Aspose.Words para .NET. Mejore la navegación de PDF configurando niveles de encabezado y esquemas ampliados.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/set-outline-options/
---
## Introducción

Cuando se trabaja con documentos, especialmente con fines profesionales o académicos, organizar el contenido de forma eficaz es fundamental. Una forma de mejorar la usabilidad de sus documentos PDF es configurando opciones de esquema. Los esquemas, o marcadores, permiten a los usuarios navegar por el documento de manera eficiente, como los capítulos de un libro. En esta guía, profundizaremos en cómo puede configurar estas opciones usando Aspose.Words para .NET, asegurando que sus archivos PDF estén bien organizados y sean fáciles de usar.

## Requisitos previos

Antes de comenzar, hay algunas cosas que deberás asegurarte de tener:

1.  Aspose.Words para .NET: asegúrese de tener instalado Aspose.Words para .NET. Si no, puedes[descarga la última versión aquí](https://releases.aspose.com/words/net/).
2. Un entorno de desarrollo .NET: necesitará un entorno de desarrollo .NET que funcione, como Visual Studio.
3. Comprensión básica de C#: la familiaridad con el lenguaje de programación C# le ayudará a seguirlo fácilmente.
4. Un documento de Word: tenga listo un documento de Word que convertirá a PDF.

## Importar espacios de nombres

Primero, deberá importar los espacios de nombres necesarios. Aquí es donde incluirá la biblioteca Aspose.Words para interactuar con su documento. Aquí se explica cómo configurarlo:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Paso 1: definir la ruta del documento

Para comenzar, deberá especificar la ruta a su documento de Word. Este es el archivo que desea convertir a PDF con opciones de esquema. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 En el fragmento de código anterior, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos. Esto le indica al programa dónde encontrar el documento de Word.

## Paso 2: configurar las opciones de guardar PDF

 A continuación, debe configurar las opciones de guardado de PDF. Esto incluye configurar cómo se deben manejar los esquemas en la salida PDF. Usarás el`PdfSaveOptions` clase para hacer esto.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
```

Ahora, configuremos las opciones del esquema. 

### Establecer niveles de esquema de encabezados

 El`HeadingsOutlineLevels` La propiedad define cuántos niveles de encabezados deben incluirse en el esquema del PDF. Por ejemplo, si lo configura en 3, incluirá hasta tres niveles de títulos en el esquema del PDF.

```csharp
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
```

### Establecer niveles de esquema ampliados

 El`ExpandedOutlineLevels`La propiedad controla cuántos niveles del esquema deben expandirse de forma predeterminada cuando se abre el PDF. Establecer esto en 1 expandirá los títulos de nivel superior, brindando una vista clara de las secciones principales.

```csharp
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Paso 3: guarde el documento como PDF

 Con las opciones configuradas, estará listo para guardar el documento como PDF. Utilizar el`Save` método de la`Document` class y pase la ruta del archivo y guarde las opciones.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Esta línea de código guarda su documento de Word como PDF, aplicando las opciones de esquema que configuró. 

## Conclusión

Configurar opciones de esquema en un documento PDF puede mejorar enormemente su navegabilidad, facilitando a los usuarios encontrar y acceder a las secciones que necesitan. Con Aspose.Words para .NET, puede configurar fácilmente estos ajustes para satisfacer sus necesidades, asegurándose de que sus documentos PDF sean lo más fáciles de usar posible.

## Preguntas frecuentes

### ¿Cuál es el propósito de configurar opciones de esquema en un PDF?

La configuración de opciones de esquema ayuda a los usuarios a navegar por documentos PDF grandes más fácilmente al proporcionar una tabla de contenido estructurada en la que se puede hacer clic.

### ¿Puedo establecer diferentes niveles de encabezado para diferentes secciones de mi documento?

No, la configuración del esquema se aplica globalmente en todo el documento. Sin embargo, puede estructurar su documento con niveles de encabezado apropiados para lograr un efecto similar.

### ¿Cómo puedo obtener una vista previa de los cambios antes de guardar el PDF?

Puede utilizar visores de PDF que admitan la navegación por esquemas para comprobar cómo aparece el esquema. Algunas aplicaciones ofrecen una función de vista previa para esto.

### ¿Es posible eliminar el esquema después de guardar el PDF?

Sí, puedes eliminar contornos utilizando el software de edición de PDF, pero esto no se puede lograr directamente con Aspose.Words una vez creado el PDF.

### ¿Qué otras opciones para guardar PDF puedo configurar con Aspose.Words?

Aspose.Words ofrece varias opciones, como configurar el nivel de cumplimiento de PDF, incrustar fuentes y ajustar la calidad de la imagen.