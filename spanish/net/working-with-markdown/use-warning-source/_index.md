---
title: Usar fuente de advertencia
linktitle: Usar fuente de advertencia
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar la fuente de advertencia con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/use-warning-source/
---

En este ejemplo, le mostraremos cómo usar la fuente de advertencia con Aspose.Words para .NET. La fuente de advertencia indica el origen de la advertencia cuando se utiliza la función de devolución de llamada.

## Paso 1: Cargar el documento

 Cargaremos un documento existente que contiene advertencias usando el`Load` metodo de la`Document` clase.

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