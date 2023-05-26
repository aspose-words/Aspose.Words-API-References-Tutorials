---
title: Leer propiedades de Active XControl
linktitle: Leer propiedades de Active XControl
second_title: Referencia de API de Aspose.Words para .NET
description: Lea las propiedades de los controles ActiveX en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

En esta guía paso a paso, le mostraremos cómo leer las propiedades de los controles ActiveX en un documento de Word utilizando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: inicialización del documento

 El primer paso es inicializar el`Document` objeto cargando el documento de Word que contiene los controles ActiveX. Asegúrese de reemplazar`MyDir` con la ruta real al directorio que contiene el documento.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Paso 2: recuperar los controles ActiveX

 En este paso, iteraremos a través de cada`Shape` del documento para recuperar los controles ActiveX y leer sus propiedades.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Ejemplo de código fuente para leer las propiedades activas de XControl usando Aspose.Words para .NET

Aquí está el código fuente completo para leer las propiedades de los controles ActiveX usando Aspose.Words para .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

