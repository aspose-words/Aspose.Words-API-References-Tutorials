---
title: Insertar documento al reemplazar
linktitle: Insertar documento al reemplazar
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo insertar un documento en reemplazo usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/clone-and-combine-documents/insert-document-at-replace/
---
En este tutorial, le explicaremos cómo insertar un documento en otro documento al reemplazarlo utilizando la función Insertar documento al reemplazar de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y realizar la inserción del documento.

## Paso 1: cargar el documento principal

Para comenzar, especifique el directorio de sus documentos y cargue el documento principal en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Paso 2: configurar las opciones de búsqueda y reemplazo

Ahora configuraremos las opciones de buscar y reemplazar especificando la dirección de búsqueda y la devolución de llamada de reemplazo para insertar un documento en otro documento. Así es cómo:

```csharp
// Configure las opciones de búsqueda y reemplazo.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Paso 3: llamar al método de reemplazo

Ahora llamaremos al método de reemplazo para buscar y reemplazar el texto especificado con una cadena vacía, usando las opciones configuradas. Así es cómo:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Código fuente de ejemplo para Insertar documento al reemplazar usando Aspose.Words para .NET

Aquí está el código fuente completo de la función Insertar documento al reemplazar Aspose.Words para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Configure las opciones de buscar y reemplazar.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Llame al método de reemplazo.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Conclusión

En este tutorial, exploramos cómo insertar un documento en otro documento durante el reemplazo usando la función Insertar documento al reemplazar de Aspose.Words para .NET. Al configurar las opciones de buscar y reemplazar y proporcionar los datos necesarios, puede ensamblar documentos dinámicamente reemplazando marcadores de posición específicos con el contenido de otras plantillas o secciones de documentos. Aspose.Words para .NET ofrece una forma potente y flexible de gestionar tareas complejas de manipulación de documentos, lo que la convierte en una herramienta valiosa para automatizar escenarios de creación de documentos e inserción de contenido.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de insertar un documento dentro de otro documento durante la sustitución?

R: Insertar un documento en otro documento durante el reemplazo le permite reemplazar dinámicamente un marcador de posición específico con el contenido de un documento separado. Esta característica es particularmente útil cuando desea ensamblar un documento más grande combinando varias plantillas o secciones de documentos predefinidas en marcadores de posición específicos.

#### P: ¿Cómo inserto un documento en otro documento durante el reemplazo usando Aspose.Words para .NET?

R: Para insertar un documento en otro documento durante el reemplazo usando Aspose.Words para .NET, siga estos pasos:
1. Cargue el documento principal que contiene los marcadores de posición en un objeto Documento.
2. Configure las opciones de buscar y reemplazar, incluida la dirección de búsqueda y reemplazar la devolución de llamada para manejar la inserción del documento.
3. Llame al método de reemplazo con el patrón de búsqueda apropiado, reemplazando los marcadores de posición con una cadena vacía, usando las opciones configuradas.

#### P: ¿Puedo personalizar el comportamiento de inserción durante el reemplazo?

R: Sí, puede personalizar el comportamiento de inserción durante el reemplazo implementando un ReplacingCallback personalizado. Al heredar de la interfaz IReplacingCallback, puede controlar cómo se insertan y fusionan los documentos según sus requisitos específicos al reemplazar los marcadores de posición.

#### P: ¿Puedo reemplazar varios marcadores de posición con documentos diferentes?

R: Sí, puede reemplazar varios marcadores de posición con diferentes documentos especificando los patrones de búsqueda adecuados para cada marcador de posición y proporcionando los documentos correspondientes que se insertarán.