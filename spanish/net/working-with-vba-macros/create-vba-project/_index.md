---
title: Crear proyecto Vba
linktitle: Crear proyecto Vba
second_title: Referencia de API de Aspose.Words para .NET
description: En este tutorial, aprenda a crear un proyecto de VBA en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-vba-macros/create-vba-project/
---

En este tutorial, le diremos cómo crear un proyecto VBA en un documento de Word utilizando la biblioteca Aspose.Words para .NET. La creación de un proyecto VBA le permite agregar un código VBA personalizado a su documento de Word. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: Definir el directorio de documentos
 Primero, debe establecer la ruta del directorio en la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cree un nuevo documento y proyecto de VBA
 A continuación, crearemos un nuevo documento instanciando el`Document` class y un proyecto de VBA vacío instanciando el`VbaProject` clase.

```csharp
// Crear un nuevo documento
Document doc = new Document();

// Crear un nuevo proyecto de VBA
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## Paso 3: Cree un nuevo módulo y especifique el código fuente de la macro
 Crearemos un nuevo módulo instanciando el`VbaModule` class y especificando el nombre de la macro, el tipo (módulo de procedimiento) y el código fuente.

```csharp
// Crear un nuevo módulo
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// Agregar el módulo al proyecto VBA
doc.VbaProject.Modules.Add(module);
```

## Paso 4: Guarde el documento
Finalmente, guardaremos el documento con el proyecto VBA creado en un archivo.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### Ejemplo de código fuente para Create Vba Project usando Aspose.Words para .NET 

```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// Cree un nuevo módulo y especifique un código fuente de macro.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// Agregar módulo al proyecto VBA.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## Conclusión
En este tutorial, vimos cómo crear un proyecto VBA en un documento de Word usando Aspose.Words para .NET. La creación de un proyecto VBA le permite agregar y personalizar el código VBA en su documento de Word. Siéntase libre de usar esta función para automatizar tareas o agregar funciones personalizadas a sus documentos de Word.
