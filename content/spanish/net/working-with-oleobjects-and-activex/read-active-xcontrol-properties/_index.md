---
title: Leer las propiedades de Active XControl desde un archivo de Word
linktitle: Leer las propiedades de Active XControl desde un archivo de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a leer las propiedades de control ActiveX de archivos de Word usando Aspose.Words para .NET en una guía paso a paso. Mejore sus habilidades de automatización de documentos.
type: docs
weight: 10
url: /es/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## Introducción

En la era digital actual, la automatización es clave para mejorar la productividad. Si está trabajando con documentos de Word que contienen controles ActiveX, es posible que necesite leer sus propiedades para diversos fines. Los controles ActiveX, como casillas de verificación y botones, pueden contener datos importantes. Con Aspose.Words para .NET, puede extraer y manipular estos datos de manera eficiente mediante programación.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1.  Aspose.Words para la biblioteca .NET: puede descargarlo desde[aquí](https://releases.aspose.com/words/net/).
2. Visual Studio o cualquier IDE de C#: para escribir y ejecutar su código.
3. Un documento de Word con controles ActiveX: por ejemplo, "controles ActiveX.docx".
4. Conocimientos básicos de C#: para seguir adelante es necesario estar familiarizado con la programación en C#.

## Importar espacios de nombres

Primero, importemos los espacios de nombres necesarios para trabajar con Aspose.Words para .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## Paso 1: cargue el documento de Word

Para comenzar, deberá cargar el documento de Word que contiene los controles ActiveX.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## Paso 2: Inicializar una cadena para contener propiedades

A continuación, inicialice una cadena vacía para almacenar las propiedades de los controles ActiveX.

```csharp
string properties = "";
```

## Paso 3: iterar a través de formas en el documento

Necesitamos recorrer todas las formas del documento para encontrar los controles ActiveX.

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        // Procesar el control ActiveX
    }
}
```

## Paso 4: extraer propiedades de los controles ActiveX

Dentro del bucle, verifique si el control es Forms2OleControl. Si es así, échalo y extrae las propiedades.

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## Paso 5: Cuente el total de controles ActiveX

Después de recorrer todas las formas, cuente el número total de controles ActiveX encontrados.

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## Paso 6: mostrar las propiedades

Finalmente, imprima las propiedades extraídas en la consola.

```csharp
Console.WriteLine("\n" + properties);
```

## Conclusión

¡Y ahí lo tienes! Ha aprendido con éxito cómo leer las propiedades del control ActiveX de un documento de Word usando Aspose.Words para .NET. Este tutorial cubrió la carga de un documento, la iteración a través de formas y la extracción de propiedades de los controles ActiveX. Si sigue estos pasos, puede automatizar la extracción de datos importantes de sus documentos de Word, mejorando la eficiencia de su flujo de trabajo.

## Preguntas frecuentes

### ¿Qué son los controles ActiveX en documentos de Word?
Los controles ActiveX son objetos interactivos integrados en documentos de Word, como casillas de verificación, botones y campos de texto, que se utilizan para crear formularios y automatizar tareas.

### ¿Puedo modificar las propiedades de los controles ActiveX usando Aspose.Words para .NET?
Sí, Aspose.Words para .NET le permite modificar las propiedades de los controles ActiveX mediante programación.

### ¿Aspose.Words para .NET es de uso gratuito?
 Aspose.Words para .NET ofrece una prueba gratuita, pero deberá comprar una licencia para poder seguir usándolo. Puedes obtener una prueba gratuita[aquí](https://releases.aspose.com/).

### ¿Puedo usar Aspose.Words para .NET con otros lenguajes .NET además de C#?
Sí, Aspose.Words para .NET se puede utilizar con cualquier lenguaje .NET, incluidos VB.NET y F#.

### ¿Dónde puedo encontrar más documentación sobre Aspose.Words para .NET?
 Puedes encontrar documentación detallada.[aquí](https://reference.aspose.com/words/net/).