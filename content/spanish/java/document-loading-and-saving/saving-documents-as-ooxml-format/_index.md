---
title: Guardar documentos en formato OOXML en Aspose.Words para Java
linktitle: Guardar documentos en formato OOXML
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a guardar documentos en formato OOXML con Aspose.Words para Java. Proteja, optimice y personalice sus archivos sin esfuerzo.
type: docs
weight: 20
url: /es/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Introducción a guardar documentos en formato OOXML en Aspose.Words para Java

En esta guía, exploraremos cómo guardar documentos en formato OOXML usando Aspose.Words para Java. OOXML (Office Open XML) es un formato de archivo utilizado por Microsoft Word y otras aplicaciones de Office. Cubriremos varias opciones y configuraciones para guardar documentos en formato OOXML.

## Requisitos previos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Words para Java configurada en su proyecto.

## Guardar un documento con cifrado de contraseña

Puede cifrar su documento con una contraseña mientras lo guarda en formato OOXML. Así es como puedes hacerlo:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Cargar el documento
Document doc = new Document("Document.docx");

// Cree OoxmlSaveOptions y establezca la contraseña
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// Guarde el documento con cifrado
doc.save("EncryptedDoc.docx", saveOptions);
```

## Configuración del cumplimiento de OOXML

Puede especificar el nivel de cumplimiento de OOXML al guardar el documento. Por ejemplo, puede configurarlo en ISO 29500:2008 (estricto). Así es cómo:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// Cargar el documento
Document doc = new Document("Document.docx");

// Optimizar para Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// Cree OoxmlSaveOptions y establezca el nivel de cumplimiento
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// Guarde el documento con la configuración de cumplimiento
doc.save("ComplianceDoc.docx", saveOptions);
```

## Actualización de la propiedad Hora del último guardado

Puede optar por actualizar la propiedad "Última hora guardada" del documento al guardarlo. Así es cómo:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Cargar el documento
Document doc = new Document("Document.docx");

// Cree OoxmlSaveOptions y habilite la actualización de la propiedad Última hora guardada
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// Guarde el documento con la propiedad actualizada.
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## Mantener los personajes de control heredados

Si su documento contiene caracteres de control heredados, puede optar por conservarlos mientras los guarda. Así es cómo:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// Cargar un documento con caracteres de control heredados
Document doc = new Document("LegacyControlChars.doc");

//Cree OoxmlSaveOptions con el formato FLAT_OPC y habilite el mantenimiento de caracteres de control heredados
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// Guarde el documento con caracteres de control heredados
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## Configuración del nivel de compresión

Puede ajustar el nivel de compresión al guardar el documento. Por ejemplo, puedes configurarlo en SUPER_FAST para una compresión mínima. Así es cómo:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// Cargar el documento
Document doc = new Document("Document.docx");

// Cree OoxmlSaveOptions y establezca el nivel de compresión
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// Guarde el documento con el nivel de compresión especificado
doc.save("FastCompressionDoc.docx", saveOptions);
```

Estas son algunas de las opciones y configuraciones clave que puede usar al guardar documentos en formato OOXML usando Aspose.Words para Java. No dude en explorar más opciones y personalizar el proceso de guardar documentos según sea necesario.

## Código fuente completo para guardar documentos en formato OOXML en Aspose.Words para Java

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## Conclusión

En esta guía completa, exploramos cómo guardar documentos en formato OOXML usando Aspose.Words para Java. Ya sea que necesite cifrar sus documentos con contraseñas, garantizar el cumplimiento de estándares OOXML específicos, actualizar las propiedades del documento, preservar los caracteres de control heredados o ajustar los niveles de compresión, Aspose.Words proporciona un conjunto versátil de herramientas para satisfacer sus necesidades.

## Preguntas frecuentes

### ¿Cómo elimino la protección con contraseña de un documento protegido con contraseña?

Para eliminar la protección con contraseña de un documento protegido con contraseña, puede abrir el documento con la contraseña correcta y luego guardarlo sin especificar una contraseña en las opciones de guardar. Esto guardará el documento sin protección con contraseña.

### ¿Puedo establecer propiedades personalizadas al guardar un documento en formato OOXML?

 Sí, puede configurar propiedades personalizadas para un documento antes de guardarlo en formato OOXML. Utilizar el`BuiltInDocumentProperties` y`CustomDocumentProperties` clases para establecer varias propiedades, como autor, título, palabras clave y propiedades personalizadas.

### ¿Cuál es el nivel de compresión predeterminado al guardar un documento en formato OOXML?

 El nivel de compresión predeterminado al guardar un documento en formato OOXML usando Aspose.Words para Java es`NORMAL` . Puede cambiar el nivel de compresión a`SUPER_FAST` o`MAXIMUM` según sea necesario.