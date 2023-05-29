---
title: Insertar campo de formulario de cuadro combinado
linktitle: Insertar campo de formulario de cuadro combinado
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar campos de formulario de cuadro combinado en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-combo-box-form-field/
---

En este ejemplo completo, aprenderá cómo insertar un campo de formulario de cuadro combinado en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar campos de formulario de cuadro combinado con propiedades personalizables a sus documentos.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: definir los elementos del cuadro combinado
A continuación, defina una matriz de elementos para el campo de formulario de cuadro combinado:

```csharp
string[] items = { "One", "Two", "Three" };
```

## Paso 3: inserte un campo de formulario de cuadro combinado
Utilice el método InsertComboBox de la clase DocumentBuilder para insertar un campo de formulario de cuadro combinado. Proporcione el nombre, la matriz de elementos y el índice seleccionado como parámetros:

```csharp
builder.InsertComboBox("DropDown", items, 0);
```

## Paso 4: Guarde el documento
Después de insertar el campo de formulario del cuadro combinado, guarde el documento en un archivo utilizando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

### Ejemplo de código fuente para insertar campo de formulario de cuadro combinado usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar un campo de formulario de cuadro combinado usando Aspose.Words para .NET:

```csharp
string[] items = { "One", "Two", "Three" };

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertComboBox("DropDown", items, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

Recuerde ajustar el código de acuerdo con sus requisitos específicos y mejorarlo con funciones adicionales según sea necesario.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar un campo de formulario de cuadro combinado en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, ahora puede mejorar sus documentos con campos de formulario de cuadro combinado interactivo.
