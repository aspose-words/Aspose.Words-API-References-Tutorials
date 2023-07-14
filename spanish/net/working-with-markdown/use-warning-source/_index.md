---
title: Usar fuente de advertencia
linktitle: Usar fuente de advertencia
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a usar la fuente de advertencia con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/use-warning-source/
---

En este ejemplo, le mostraremos cómo usar la fuente de advertencia con Aspose.Words para .NET. La fuente de advertencia indica el origen de la advertencia cuando se utiliza la función de devolución de llamada.

## Paso 1: Cargar el documento

 Cargaremos un documento existente que contenga advertencias usando el`Load` metodo de la`Document` clase.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Paso 3: uso de la fuente de advertencia

 Usaremos la fuente de advertencia configurando el documento`WarningCallback` propiedad a una colección de`WarningInfo` objetos.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Paso 4: Guardar el documento

Finalmente, podemos guardar el documento en el formato deseado.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Ejemplo de código fuente para usar la fuente de advertencia con Aspose.Words para .NET

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

¡Felicidades! Ahora ha aprendido a usar la fuente de advertencia con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Podemos personalizar la apariencia de la etiqueta de "Advertencia"?

R: El formato de la etiqueta "Advertencia" depende del renderizador Markdown utilizado. En la mayoría de los casos, puede personalizar el aspecto utilizando CSS para orientar el`blockquote` etiqueta en su documento.

#### P: ¿Es posible agregar íconos a la etiqueta "Advertencia"?

 R: Sí, es posible agregar íconos a la etiqueta "Advertencia" usando código HTML en su documento Markdown. Puede insertar un`span` etiqueta con la clase adecuada para mostrar un icono junto al texto de advertencia.

#### P: ¿La etiqueta de "Advertencia" es compatible con todos los lectores de Markdown?

 R: La compatibilidad de la etiqueta "Advertencia" depende de la representación de Markdown utilizada. La mayoría de los lectores de Markdown admitirán el`blockquote` etiqueta para mostrar el texto resaltado, pero la apariencia exacta puede variar.