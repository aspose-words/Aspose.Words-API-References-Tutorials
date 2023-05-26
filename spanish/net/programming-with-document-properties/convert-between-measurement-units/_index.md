---
title: Convertir entre unidades de medida
linktitle: Convertir entre unidades de medida
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para convertir entre unidades de medida en un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/convert-between-measurement-units/
---

En este tutorial, lo guiaremos a través del código fuente de C# para convertir entre unidades de medida con Aspose.Words para .NET. Esta característica le permite especificar márgenes, distancias de encabezado y pie de página, etc. en diferentes unidades de medida.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Creando el Documento y el Constructor

En este paso crearemos un nuevo documento e inicializaremos el constructor. Usa el siguiente código:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Configurar unidades de medida

Ahora convertiremos los valores de márgenes, distancias de encabezado y pie de página, etc. en diferentes unidades de medida. Utilice el siguiente código para especificar valores en unidades de medida específicas:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Este código utiliza el`ConvertUtil` clase de Aspose.Words para convertir los valores especificados a pulgadas (`InchToPoint` ). También puede utilizar otros métodos de conversión disponibles en el`ConvertUtil` clase para convertir valores a otras unidades de medida.

### Ejemplo de código fuente para convertir entre unidades de medida usando Aspose.Words para .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Ahora ha aprendido cómo convertir entre unidades de medida al especificar márgenes, distancias de encabezado y pie de página, etc. en un documento usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede especificar fácilmente los valores en las unidades de medida deseadas en sus propios documentos.