---
title: Insertar campo usando el generador de campos
linktitle: Insertar campo usando el generador de campos
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar campos personalizados en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-field-using-field-builder/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Insertar un campo usando FieldBuilder" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código proporcionado, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear el documento

Empezamos creando un nuevo documento.

```csharp
Document doc = new Document();
```

## Paso 3: construir el campo IF usando FieldBuilder

Usamos la clase FieldBuilder para construir un campo IF con dos campos MERGEFIELD anidados. En este ejemplo, el campo SI muestra el nombre y apellido según una condición.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Paso 4: Insertar el campo SI en el documento

 Usamos el`BuildAndInsert()` Método para crear e insertar el campo IF en una ubicación específica del documento.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Código fuente de ejemplo para insertar un campo usando FieldBuilder con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos.
Document doc = new Document();

// Construcción del campo IF utilizando FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Inserte el campo SI en el documento.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

En este ejemplo, creamos un nuevo documento, construimos un campo IF con campos MERGEFIELD anidados y luego insertamos ese campo en el documento en una ubicación específica. Luego, el documento se guarda con un nombre de archivo específico.

### Preguntas frecuentes

#### P: ¿Qué es un constructor de campos en Aspose.Words?

R: Un generador de campos en Aspose.Words es una poderosa herramienta para crear y manipular campos en un documento de Word. Ofrece funciones avanzadas para crear y personalizar campos, incluida la inserción de códigos de campo y la gestión de opciones de formato.

#### P: ¿Qué tipos de campos se pueden insertar usando el generador de campos?

R: El generador de campos en Aspose.Words le permite insertar diferentes tipos de campos en un documento de Word. A continuación se muestran algunos ejemplos de tipos de campos utilizados habitualmente:

- MERGEFIELD: se utiliza para fusionar datos de fuentes externas.
- FECHA: muestra la fecha actual.
- PÁGINA: muestra el número de página actual.
- SI: permite condicionar la visualización de un contenido según una condición.
- TOC: genera automáticamente una tabla de contenido basada en los estilos de título del documento.

#### P: ¿Cómo personalizar los campos insertados con el generador de campos?

R: El creador de campos ofrece opciones de personalización para los campos insertados. Puede utilizar métodos y propiedades del constructor de campos para establecer opciones como formato de campo, argumentos, modificadores y valores predeterminados. Por ejemplo, puede configurar el formato de fecha, el formato de número, el separador de miles, etc.
  