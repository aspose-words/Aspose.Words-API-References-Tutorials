---
title: Cultura de actualización de campo
linktitle: Cultura de actualización de campo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a actualizar la cultura de campo en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/field-update-culture/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la función "Actualización de cultura de campo" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear el documento y el generador de documentos

Comenzamos creando un nuevo documento y un generador de documentos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Insertar el campo de tiempo

 usamos el`InsertField()` para insertar un campo de tiempo en el documento.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Esto insertará un campo de tiempo en el documento.

## Paso 4: Configuración de la cultura de actualización de campo

Configuramos las opciones de campo para especificar que la cultura de actualización de campo debe basarse en el código de campo.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Estas opciones determinan la referencia cultural utilizada para actualizar campos.

### Ejemplo de código fuente para actualizar Field Culture con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento y el generador de documentos.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte el campo de tiempo.
builder. InsertField(FieldType.FieldTime, true);

//Configure la referencia cultural de actualización de campo.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Guarde el documento.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

En este ejemplo, creamos un nuevo documento, insertamos un campo de tiempo y configuramos la referencia cultural de actualización de campo. Luego guardamos el documento con un nombre de archivo específico.

Esto concluye nuestra guía sobre el uso de la función "Actualizar cultura de campo" con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cuál es la cultura de actualización de campo en Aspose.Words?

R: La cultura de actualización de campo en Aspose.Words se refiere a la cultura utilizada para formatear y actualizar valores de campo en un documento de Word. La referencia cultural determina cómo se presentan los números, las fechas y otros datos en los campos cuando se actualizan.

#### P: ¿Cómo configurar la cultura de actualización para campos en un documento de Word con Aspose.Words?

R: Para configurar la cultura de actualización para los campos en un documento de Word con Aspose.Words, puede seguir estos pasos:

1. Importe la clase Document del espacio de nombres Aspose.Words.
2. Cree una instancia de Documento cargando su documento existente.
3. Use la propiedad Document.UpdateFieldsCultureInfo para establecer la cultura de actualización para los campos.

#### P: ¿Cuáles son las culturas admitidas para actualizar campos en Aspose.Words?

R: Aspose.Words admite diferentes culturas para actualizar campos. Puede especificar cualquier referencia cultural admitida por el sistema operativo. Por ejemplo, "en-US" para inglés americano, "fr-FR" para francés, "de-DE" para alemán, etc.

#### P: ¿Es posible establecer una referencia cultural específica para un campo individual en lugar de para todo el documento?

R: Sí, es posible establecer una referencia cultural específica para un campo individual en lugar de para todo el documento. En Aspose.Words, cada campo tiene una propiedad Formato que se puede usar para establecer la cultura de formato específica para ese campo. Esto le permite controlar cómo se muestra y actualiza este campo independientemente de otros campos en el documento.

#### P: ¿Cómo puedo verificar la referencia cultural de actualización de campo definida actualmente en un documento de Word?

R: Para verificar la referencia cultural de actualización de campo definida actualmente en un documento de Word, puede usar la propiedad Document.UpdateFieldsCultureInfo. Esta propiedad devuelve el objeto CultureInfo que representa la referencia cultural utilizada actualmente para establecer actualizaciones de campo.