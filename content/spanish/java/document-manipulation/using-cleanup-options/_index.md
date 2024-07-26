---
title: Uso de opciones de limpieza en Aspose.Words para Java
linktitle: Usar opciones de limpieza
second_title: API de procesamiento de documentos Java Aspose.Words
description: Mejore la claridad del documento con Aspose.Words para las opciones de limpieza de Java. Aprenda cómo eliminar párrafos vacíos, regiones no utilizadas y más.
type: docs
weight: 10
url: /es/java/document-manipulation/using-cleanup-options/
---

## Introducción al uso de opciones de limpieza en Aspose.Words para Java

En este tutorial, exploraremos cómo usar las opciones de limpieza en Aspose.Words para Java para manipular y limpiar documentos durante el proceso de combinación de correspondencia. Las opciones de limpieza le permiten controlar varios aspectos de la limpieza de documentos, como eliminar párrafos vacíos, regiones no utilizadas y más.

## Requisitos previos

 Antes de comenzar, asegúrese de tener la biblioteca Aspose.Words para Java integrada en su proyecto. Puedes descargarlo desde[aquí](https://releases.aspose.com/words/java/).

## Paso 1: eliminar párrafos vacíos

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar campos de combinación
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Establecer opciones de limpieza
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Habilitar párrafos de limpieza con signos de puntuación
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Ejecutar combinación de correspondencia
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// guardar el documento
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

En este ejemplo, creamos un nuevo documento, insertamos campos de combinación y configuramos las opciones de limpieza para eliminar párrafos vacíos. Además, permitimos la eliminación de párrafos con signos de puntuación. Después de ejecutar la combinación de correspondencia, el documento se guarda con la limpieza especificada aplicada.

## Paso 2: eliminar regiones no fusionadas

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Establecer opciones de limpieza para eliminar regiones no utilizadas
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Ejecutar combinación de correspondencia con regiones
doc.getMailMerge().executeWithRegions(data);

// guardar el documento
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

En este ejemplo, abrimos un documento existente con regiones de combinación, configuramos las opciones de limpieza para eliminar regiones no utilizadas y luego ejecutamos la combinación de correspondencia con datos vacíos. Este proceso elimina automáticamente las regiones no utilizadas del documento.

## Paso 3: eliminar campos vacíos

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Establecer opciones de limpieza para eliminar campos vacíos
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Ejecutar combinación de correspondencia
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// guardar el documento
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

En este ejemplo, abrimos un documento con campos de combinación, configuramos las opciones de limpieza para eliminar campos vacíos y ejecutamos la combinación de correspondencia con datos. Después de la combinación, todos los campos vacíos se eliminarán del documento.

## Paso 4: eliminar campos no utilizados

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Establecer opciones de limpieza para eliminar campos no utilizados
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Ejecutar combinación de correspondencia
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// guardar el documento
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

En este ejemplo, abrimos un documento con campos de combinación, configuramos las opciones de limpieza para eliminar los campos no utilizados y ejecutamos la combinación de correspondencia con datos. Después de la combinación, todos los campos no utilizados se eliminarán del documento.

## Paso 5: eliminar campos contenedores

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Establecer opciones de limpieza para eliminar los campos que los contienen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Ejecutar combinación de correspondencia
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// guardar el documento
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

En este ejemplo, abrimos un documento con campos de combinación, configuramos las opciones de limpieza para eliminar los campos que lo contienen y ejecutamos la combinación de correspondencia con datos. Después de la combinación, los campos se eliminarán del documento.

## Paso 6: eliminar filas de tabla vacías

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Establecer opciones de limpieza para eliminar filas de tabla vacías
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Ejecutar combinación de correspondencia
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// guardar el documento
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

En este ejemplo, abrimos un documento con una tabla y fusionamos campos, configuramos las opciones de limpieza para eliminar filas vacías de la tabla y ejecutamos la combinación de correspondencia con datos. Después de la combinación, cualquier fila vacía de la tabla se eliminará del documento.

## Conclusión

En este tutorial, ha aprendido cómo utilizar las opciones de limpieza en Aspose.Words para Java para manipular y limpiar documentos durante el proceso de combinación de correspondencia. Estas opciones brindan un control detallado sobre la limpieza de documentos, lo que le permite crear documentos pulidos y personalizados con facilidad.

## Preguntas frecuentes

### ¿Cuáles son las opciones de limpieza en Aspose.Words para Java?

Las opciones de limpieza en Aspose.Words para Java son configuraciones que le permiten controlar varios aspectos de la limpieza de documentos durante el proceso de combinación de correspondencia. Le permiten eliminar elementos innecesarios, como párrafos vacíos, regiones no utilizadas y más, garantizando que su documento final esté bien estructurado y pulido.

### ¿Cómo puedo eliminar párrafos vacíos de mi documento?

 Para eliminar párrafos vacíos de su documento usando Aspose.Words para Java, puede configurar el`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` opción a verdadero. Esto eliminará automáticamente los párrafos que no tienen contenido, lo que dará como resultado un documento más limpio.

###  ¿Cuál es el propósito de la`REMOVE_UNUSED_REGIONS` cleanup option?

 El`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` La opción se utiliza para eliminar regiones de un documento que no tienen datos correspondientes durante el proceso de combinación de correspondencia. Ayuda a mantener su documento ordenado al eliminar los marcadores de posición no utilizados.

### ¿Puedo eliminar filas de tabla vacías de un documento usando Aspose.Words para Java?

 Sí, puede eliminar filas de tabla vacías de un documento configurando el`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`opción de limpieza en verdadero. Esto eliminará automáticamente cualquier fila de la tabla que no contenga datos, lo que garantizará una tabla bien estructurada en su documento.

###  ¿Qué sucede cuando configuro el`REMOVE_CONTAINING_FIELDS` option?

 Configurando el`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` La opción eliminará todo el campo de combinación, incluido el párrafo que lo contiene, del documento durante el proceso de combinación de correspondencia. Esto es útil cuando desea eliminar campos de combinación y su texto asociado.

### ¿Cómo puedo eliminar los campos de combinación no utilizados de mi documento?

 Para eliminar campos de combinación no utilizados de un documento, puede configurar el`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` opción a verdadero. Esto eliminará automáticamente los campos de combinación que no se completan durante la combinación de correspondencia, lo que dará como resultado un documento más limpio.

###  Cuál es la diferencia entre`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 El`REMOVE_EMPTY_FIELDS` La opción elimina los campos de combinación que no tienen datos o están vacíos durante el proceso de combinación de correspondencia. Por otra parte, el`REMOVE_UNUSED_FIELDS`La opción elimina los campos de combinación que no se completan con datos durante la combinación. La elección entre ellos depende de si desea eliminar campos sin contenido o aquellos que no se utilizan en la operación de combinación específica.

### ¿Cómo puedo habilitar la eliminación de párrafos con signos de puntuación?

 Para habilitar la eliminación de párrafos con signos de puntuación, puede configurar el`cleanupParagraphsWithPunctuationMarks` opción en verdadero y especifique los signos de puntuación que se considerarán para la limpieza. Esto le permite crear un documento más refinado eliminando párrafos innecesarios que solo contienen puntuación.

### ¿Puedo personalizar las opciones de limpieza en Aspose.Words para Java?

Sí, puede personalizar las opciones de limpieza según sus necesidades específicas. Puede elegir qué opciones de limpieza aplicar y configurarlas según los requisitos de limpieza de su documento, asegurándose de que su documento final cumpla con los estándares deseados.