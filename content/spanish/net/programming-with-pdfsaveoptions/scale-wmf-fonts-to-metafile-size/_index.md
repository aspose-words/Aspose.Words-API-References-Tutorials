---
title: Reduzca el tamaño del PDF escalando fuentes Wmf al tamaño de metarchivo
linktitle: Reduzca el tamaño del PDF escalando fuentes Wmf al tamaño de metarchivo
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para reducir el tamaño de un PDF escalando fuentes WMF al tamaño de un metarchivo al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Este artículo proporciona una guía paso a paso sobre cómo reducir el tamaño de un PDF con la función de escalar fuentes WMF al tamaño de metarchivo con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo habilitar o deshabilitar el escalado de fuentes WMF al convertir a PDF.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "WMF con text.docx" y está ubicado en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Paso 3: configurar las opciones de representación de metarchivos

 Para habilitar o deshabilitar el escalado de fuentes WMF al tamaño de metarchivo, debemos configurar el`MetafileRenderingOptions` objeto. En este ejemplo, deshabilitamos la escala de fuente configurando el`ScaleWmfFontsToMetafileSize`propiedad a`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Paso 4: Configurar las opciones de guardar como PDF con opciones de representación de metarchivos

Finalmente, podemos configurar las opciones de guardar en PDF utilizando las opciones de representación de metarchivos configuradas anteriormente.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Paso 5: guarde el documento como PDF con opciones de representación de metarchivos

Guarde el documento en formato PDF utilizando las opciones de guardado previamente configuradas.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Eso es todo ! Ha habilitado o deshabilitado con éxito la escala de fuente WMF al tamaño de metarchivo al realizar la conversión.

un documento PDF usando Aspose.Words para .NET.

### Código fuente de ejemplo para escalar fuentes WMF al tamaño de metarchivo con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Si Aspose.Words no puede representar correctamente algunos de los registros del metarchivo en gráficos vectoriales
	// luego Aspose.Words representa este metarchivo en un mapa de bits.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Conclusión

En este tutorial, explicamos cómo habilitar o deshabilitar el cambio de tamaño de las fuentes WMF al tamaño de metarchivo en un documento PDF usando Aspose.Words para .NET. Si sigue los pasos descritos, puede controlar fácilmente si se debe cambiar el tamaño de las fuentes WMF para que coincidan con el tamaño del metarchivo al convertirlas a un documento PDF. Esto puede ayudarle a reducir el tamaño del archivo PDF generado y mejorar el rendimiento de renderizado. Asegúrese de especificar la ruta correcta a sus documentos y configurar las opciones de representación del metarchivo según sea necesario.

### Preguntas frecuentes

#### P: ¿Qué significa cambiar el tamaño de las fuentes WMF al tamaño de metarchivo en un documento PDF?
R: Cambiar el tamaño de las fuentes WMF al tamaño de metarchivo en un documento PDF es una función que controla si las fuentes WMF deben escalarse para que coincidan con el tamaño del metarchivo al convertirlas a un documento PDF. Cuando esta característica está habilitada, las fuentes WMF se escalan para que coincidan con el tamaño del metarchivo, lo que puede reducir el tamaño del documento PDF generado.

#### P: ¿Cómo puedo usar Aspose.Words para .NET para habilitar o deshabilitar el cambio de tamaño de las fuentes WMF al tamaño de metarchivo en un documento PDF?
R: Para habilitar o deshabilitar el cambio de tamaño de las fuentes WMF al tamaño de metarchivo en un documento PDF usando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENT DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento que desea procesar utilizando el`Document` clase y especifique la ruta al documento de Word en el directorio de documentos especificado.

 Configure las opciones de representación del metarchivo creando una instancia del`MetafileRenderingOptions` clase y establecer el`ScaleWmfFontsToMetafileSize`propiedad a`true` para permitir el escalado de fuentes WMF al tamaño de metarchivo, o para`false` para desactivar esta función.

 Configure las opciones de guardar como PDF creando una instancia del`PdfSaveOptions` class y usando las opciones de representación de metarchivos configuradas anteriormente.

 Guarde el documento en formato PDF utilizando el`Save` método de la`Document` clase que especifica la ruta y las opciones de guardado.

#### P: ¿Cuáles son los beneficios de cambiar el tamaño de las fuentes WMF al tamaño de metarchivo en un documento PDF?
R: Las ventajas de cambiar el tamaño de las fuentes WMF al tamaño de metarchivo en un documento PDF son:

Reducción del tamaño del archivo PDF: cambiar el tamaño de las fuentes WMF al tamaño del metarchivo puede reducir el tamaño del documento PDF generado adaptando el tamaño de la fuente a las necesidades del metarchivo.

Rendimiento mejorado: al ajustar el tamaño de las fuentes WMF a las dimensiones del metarchivo, la representación del documento PDF puede ser más rápida y eficiente.