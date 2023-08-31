---
title: Usar fuente de advertencia
linktitle: Usar fuente de advertencia
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar la fuente de advertencia con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/use-warning-source/
---

En este ejemplo, le mostraremos cómo utilizar la fuente de advertencia con Aspose.Words para .NET. La fuente de advertencia indica el origen de la advertencia cuando se utiliza la función de devolución de llamada.

## Paso 1: cargar el documento

 Cargaremos un documento existente que contiene advertencias usando el`Load` método de la`Document` clase.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Paso 3: usar la fuente de advertencia

 Usaremos la fuente de advertencia configurando el documento`WarningCallback` propiedad a una colección de`WarningInfo` objetos.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Paso 4: guardar el documento

Finalmente, podremos guardar el documento en el formato deseado.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Código fuente de ejemplo para utilizar el origen de advertencia con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

¡Enhorabuena! Ahora ha aprendido a utilizar la fuente de advertencia con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Podemos personalizar la apariencia de la etiqueta "Advertencia"?

R: El formato de la etiqueta "Advertencia" depende del renderizador de Markdown utilizado. En la mayoría de los casos, puede personalizar el aspecto utilizando CSS para orientar el`blockquote` etiqueta en su documento.

#### P: ¿Es posible agregar íconos a la etiqueta "Advertencia"?

 R: Sí, es posible agregar íconos a la etiqueta "Advertencia" usando código HTML en su documento Markdown. Puedes insertar un`span` etiqueta con la clase adecuada para mostrar un icono junto al texto de advertencia.

#### P: ¿La etiqueta "Advertencia" es compatible con todos los lectores Markdown?

 R: La compatibilidad de la etiqueta "Advertencia" depende del renderizado de Markdown utilizado. La mayoría de los lectores de Markdown apoyarán el`blockquote` etiqueta para mostrar el texto resaltado, pero la apariencia exacta puede variar.