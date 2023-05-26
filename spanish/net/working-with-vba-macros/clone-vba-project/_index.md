---
title: Clonar Proyecto Vba
linktitle: Clonar Proyecto Vba
second_title: Referencia de API de Aspose.Words para .NET
description: En este tutorial, aprenda a clonar un proyecto de VBA desde un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-vba-macros/clone-vba-project/
---

En este tutorial te vamos a contar cómo clonar un proyecto VBA desde un documento de Word con macros usando la librería Aspose.Words para .NET. La clonación de un proyecto VBA le permite copiar todo el código VBA de un documento fuente a otro documento. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto
- Un documento de Word que contiene un proyecto de VBA que desea clonar

## Paso 1: Definir el directorio de documentos
 Primero, debe establecer la ruta del directorio en la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento de origen
continuación, cargaremos el documento de origen de Word, que contiene el proyecto de VBA que queremos clonar.

```csharp
// Cargue el documento de origen
Document doc = new Document(dataDir + "VBA project.docm");
```

## Paso 3: Cree un nuevo documento con el proyecto VBA clonado
Crearemos un nuevo documento con un proyecto de VBA vacío y clonaremos el proyecto de VBA del documento de origen.

```csharp
// Cree un nuevo documento con un proyecto de VBA vacío
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };
```

## Paso 4: Guarde el documento de destino
Finalmente, guardaremos el documento de destino junto con el proyecto VBA clonado en un archivo.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");
```

### Ejemplo de código fuente para Clone Vba Project usando Aspose.Words para .NET 
```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");

```

## Conclusión
En este tutorial, vimos cómo clonar un proyecto VBA desde un documento de Word con macros usando Aspose.Words para .NET. La clonación de proyectos VBA le permite copiar todo el código VBA de un documento fuente a otro documento. Siéntase libre de usar esta función para organizar y administrar sus macros en diferentes documentos.
