---
title: Lea las propiedades de Active XControl desde un archivo de Word
linktitle: Lea las propiedades de Active XControl desde un archivo de Word
second_title: Referencia de API de Aspose.Words para .NET
description: Lea las propiedades de los controles ActiveX en un archivo de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

En esta guía paso a paso, le mostraremos cómo leer las propiedades de los controles ActiveX en un archivo de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

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

## Conclusión

Esta guía le mostró cómo leer las propiedades de los controles ActiveX en un archivo de Word usando Aspose.Words para .NET. Siguiendo los pasos descritos, puede inicializar el documento, recuperar los controles ActiveX y leer sus propiedades. Utilice el código de muestra proporcionado como punto de partida y personalícelo según sus necesidades específicas.

Leer las propiedades de los controles ActiveX le permite extraer información importante de sus archivos de Word que contienen estos controles. Aspose.Words para .NET ofrece potentes funciones para trabajar con controles ActiveX y automatizar el procesamiento de documentos.

### preguntas frecuentes

#### P: ¿Cuál es el primer paso para leer las propiedades de los controles ActiveX en un archivo de Word?

 R: El primer paso es inicializar el`Document` objeto cargando el documento de Word que contiene los controles ActiveX. Asegúrese de reemplazar`MyDir` con la ruta real al directorio que contiene el documento.

#### P: ¿Cómo introduzco controles ActiveX en el documento?

 R: Para recuperar los controles ActiveX, debe iterar a través de cada`Shape` del documento y comprobar si se trata de un control ActiveX. Utilizar el`OleFormat` propiedad de`Shape` para acceder a la`OleControl` objeto y recuperar las propiedades necesarias.

#### P: ¿Qué propiedades de los controles ActiveX puedo leer?

R: Puede leer varias propiedades de los controles ActiveX, como el título, el valor, el estado habilitado o deshabilitado, el tipo y los childNodes asociados con el control.

#### P: ¿Cómo puedo obtener el número total de controles ActiveX en el documento?

 R: Para obtener el número total de controles ActiveX en el documento, puede usar el`GetChildNodes` metodo de la`Document` objeto que especifica el`NodeType.Shape` tipo e incluyendo los nodos secundarios.