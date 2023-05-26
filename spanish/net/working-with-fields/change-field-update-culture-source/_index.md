---
title: Cambiar fuente de cultura de actualización de campo
linktitle: Cambiar fuente de cultura de actualización de campo
second_title: Referencia de API de Aspose.Words para .NET
description: Cambiar la fuente de cultura de actualización de campo, guía paso a paso para modificar la fuente de cultura en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/change-field-update-culture-source/
---

En este tutorial, lo guiaremos a través del proceso de cambio de la fuente cultural de actualización de campo en documentos de Word usando Aspose.Words para .NET. Al modificar la fuente de referencia cultural, puede controlar el formato de la fecha durante la actualización de campos y las operaciones de combinación de correspondencia. Le proporcionaremos el código fuente de C# necesario y las instrucciones paso a paso para lograrlo.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un documento y DocumentBuilder
Para comenzar, cree una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Insertar contenido con una configuración regional específica
A continuación, establezca la configuración regional en alemán e inserte campos con formato de fecha:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

En el código anterior, configuramos la configuración regional de la fuente en alemán (ID de configuración regional 1031) e insertamos dos campos con un formato de fecha específico.

## Paso 3: cambiar la fuente cultural de actualización de campo
Para cambiar la fuente de cultura de actualización de campo, use la clase FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

En este ejemplo, configuramos la cultura utilizada durante la actualización del campo para que se elija de la cultura utilizada por el campo.

## Paso 4: realizar la combinación de correspondencia
Realice una operación de combinación de correspondencia y especifique el valor de fecha para el campo "Fecha2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

En este fragmento de código, ejecutamos la operación de combinación de correspondencia y proporcionamos un valor de fecha y hora para el campo "Fecha2".

## Paso 5: Guarde el documento
Guarde el documento modificado en un archivo utilizando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Código fuente de ejemplo para cambiar la fuente cultural de actualización de campo usando Aspose.Words para .NET
Aquí está el código fuente completo para cambiar la fuente de cultura de actualización de campo en documentos de Word usando Aspose.Words para .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo cambiar la fuente de cultura de actualización de campo en documentos de Word usando Aspose.Words para .NET. Al seguir la guía paso a paso y utilizar el código fuente provisto, ahora puede controlar la referencia cultural utilizada para el formato de fecha durante las operaciones de actualización de campos y combinación de correspondencia. Personalice la fuente de cultivo de acuerdo con sus requisitos para garantizar una fecha precisa y consistente.