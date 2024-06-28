---
title: Cambiar fuente de cultura de actualización de campo
linktitle: Cambiar fuente de cultura de actualización de campo
second_title: API de procesamiento de documentos Aspose.Words
description: Cambiar fuente de cultura de actualización de campo, guía paso a paso para modificar la fuente de cultura en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/change-field-update-culture-source/
---

En este tutorial, lo guiaremos a través del proceso de cambiar la fuente cultural de actualización de campos en documentos de Word usando Aspose.Words para .NET. Al modificar la fuente cultural, puede controlar el formato de la fecha durante las operaciones de actualización de campos y combinación de correspondencia. Le proporcionaremos el código fuente C# necesario e instrucciones paso a paso para lograrlo.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: crear un documento y DocumentBuilder
Para comenzar, cree una instancia de la clase Documento y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: insertar contenido con una configuración regional específica
A continuación, configure la configuración regional en alemán e inserte campos con formato de fecha:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

En el código anterior, configuramos la configuración regional de la fuente en alemán (ID de configuración regional 1031) e insertamos dos campos con un formato de fecha específico.

## Paso 3: Cambiar la fuente cultural de actualización del campo
Para cambiar la fuente cultural de actualización de campo, use la clase FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

En este ejemplo, configuramos la cultura utilizada durante la actualización del campo para que se elija entre la cultura utilizada por el campo.

## Paso 4: realizar combinación de correspondencia
Realice una operación de combinación de correspondencia y especifique el valor de fecha para el campo "Fecha2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

En este fragmento de código, ejecutamos la operación de combinación de correspondencia y proporcionamos un valor de Fecha y hora para el campo "Fecha2".

## Paso 5: guarde el documento
Guarde el documento modificado en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Código fuente de ejemplo para cambiar la fuente cultural de actualización de campos usando Aspose.Words para .NET
Aquí está el código fuente completo para cambiar la fuente cultural de actualización de campos en documentos de Word usando Aspose.Words para .NET:

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
¡Felicidades! Ha aprendido con éxito cómo cambiar la fuente cultural de actualización de campo en documentos de Word usando Aspose.Words para .NET. Si sigue la guía paso a paso y utiliza el código fuente proporcionado, ahora puede controlar la cultura utilizada para el formato de fecha durante las operaciones de actualización de campos y combinación de correspondencia. Personalice la fuente de cultivo según sus requisitos para garantizar una fecha precisa y coherente.

### Preguntas frecuentes

#### P: ¿Cómo puedo cambiar la fuente cultural de actualización del campo en Aspose.Words para .NET?

 R: Para cambiar la fuente cultural de actualización de campo en Aspose.Words para .NET, puede usar el`Document.FieldOptions.CultureSource` propiedad y establecer su valor en`FieldCultureSource.FieldCode` o`FieldCultureSource.CurrentThread` . Por ejemplo, puedes usar`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` para utilizar la cultura definida en el código de campo.

#### P: ¿Cómo puedo especificar una cultura específica para actualizar campos en Aspose.Words para .NET?

 R: Para especificar una cultura específica para actualizar campos en Aspose.Words para .NET, puede usar el`Document.FieldOptions.FieldUpdateCultureInfo` propiedad y establecer el`CultureInfo` objeto correspondiente a la cultura deseada. Por ejemplo, puedes usar`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` para especificar la cultura francesa (Francia).

#### P: ¿Es posible desactivar la actualización automática de campos en Aspose.Words para .NET?

 R: Sí, es posible desactivar la actualización automática de campos en Aspose.Words para .NET. Puedes usar el`Document.FieldOptions.UpdateFields` propiedad y configúrelo en`false` para evitar que los campos se actualicen automáticamente. Esto le permite controlar manualmente la actualización de los campos según sea necesario.

#### P: ¿Cómo puedo actualizar manualmente los campos del documento en Aspose.Words para .NET?

 R: Para actualizar manualmente los campos de un documento en Aspose.Words para .NET, puede utilizar el`Field.Update` método para cada campo individualmente. Por ejemplo, puedes usar`field.Update()` para actualizar el campo específico.