---
title: Código de campo
linktitle: Código de campo
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para obtener el código de campo y el resultado del campo en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/field-code/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Obtener código de campo" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargar el documento

El primer paso es cargar el documento donde desea obtener los códigos de campo.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Asegúrese de reemplazar "Hipervínculos.docx" con el nombre de su propio archivo.

## Paso 3: Navegar por los campos del documento

 usamos un`foreach` bucle para recorrer todos los campos presentes en el documento.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 En cada iteración del ciclo, obtenemos el código de campo usando el`GetFieldCode()` método. También almacenamos el resultado del campo en una variable.

### Ejemplo de código fuente para Obtener código de campo con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Recorra los campos del documento.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Haga algo con el código y el resultado del campo.
}
```

En este ejemplo, cargamos un documento y luego recorrimos todos los campos presentes en el documento. En cada iteración, obtuvimos el código y el resultado del campo. Puede agregar su propia lógica para procesar el código y los campos de resultados según sea necesario.

Esto concluye nuestra guía sobre el uso de la función "Obtener código de campo" con Aspose.Words para .NET.