---
title: Speichern von Dokumenten im OOXML-Format in Aspose.Words für Java
linktitle: Dokumente im OOXML-Format speichern
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für Java Dokumente im OOXML-Format speichern. Sichern, optimieren und passen Sie Ihre Dateien mühelos an.
type: docs
weight: 20
url: /de/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Einführung in das Speichern von Dokumenten im OOXML-Format in Aspose.Words für Java

In diesem Leitfaden erfahren Sie, wie Sie mit Aspose.Words für Java Dokumente im OOXML-Format speichern. OOXML (Office Open XML) ist ein Dateiformat, das von Microsoft Word und anderen Office-Anwendungen verwendet wird. Wir behandeln verschiedene Optionen und Einstellungen zum Speichern von Dokumenten im OOXML-Format.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass in Ihrem Projekt die Aspose.Words for Java-Bibliothek eingerichtet ist.

## Speichern eines Dokuments mit Passwortverschlüsselung

Sie können Ihr Dokument beim Speichern im OOXML-Format mit einem Passwort verschlüsseln. So können Sie es machen:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Laden Sie das Dokument
Document doc = new Document("Document.docx");

// Erstellen Sie OoxmlSaveOptions und legen Sie das Passwort fest
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// Speichern Sie das Dokument verschlüsselt
doc.save("EncryptedDoc.docx", saveOptions);
```

## Festlegen der OOXML-Konformität

Sie können den OOXML-Konformitätsgrad beim Speichern des Dokuments angeben. Sie können es beispielsweise auf ISO 29500:2008 (streng) einstellen. Hier ist wie:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// Laden Sie das Dokument
Document doc = new Document("Document.docx");

// Optimieren Sie für Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// Erstellen Sie OoxmlSaveOptions und legen Sie die Konformitätsstufe fest
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// Speichern Sie das Dokument mit der Compliance-Einstellung
doc.save("ComplianceDoc.docx", saveOptions);
```

## Aktualisierung der Eigenschaft „Letzte gespeicherte Zeit“.

Sie können die Eigenschaft „Letzte gespeicherte Zeit“ des Dokuments beim Speichern aktualisieren. Hier ist wie:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Laden Sie das Dokument
Document doc = new Document("Document.docx");

// Erstellen Sie OoxmlSaveOptions und aktivieren Sie die Aktualisierung der Eigenschaft „Letzte gespeicherte Zeit“.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// Speichern Sie das Dokument mit der aktualisierten Eigenschaft
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## Behalten Sie die alten Kontrollcharaktere bei

Wenn Ihr Dokument ältere Steuerzeichen enthält, können Sie diese beim Speichern beibehalten. Hier ist wie:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// Laden Sie ein Dokument mit alten Steuerzeichen
Document doc = new Document("LegacyControlChars.doc");

//Erstellen Sie OoxmlSaveOptions mit dem FLAT_OPC-Format und aktivieren Sie die Beibehaltung älterer Steuerzeichen
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// Speichern Sie das Dokument mit alten Steuerzeichen
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## Komprimierungsstufe einstellen

Sie können die Komprimierungsstufe beim Speichern des Dokuments anpassen. Sie können es beispielsweise für eine minimale Komprimierung auf SUPER_FAST einstellen. Hier ist wie:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// Laden Sie das Dokument
Document doc = new Document("Document.docx");

// Erstellen Sie OoxmlSaveOptions und legen Sie die Komprimierungsstufe fest
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// Speichern Sie das Dokument mit der angegebenen Komprimierungsstufe
doc.save("FastCompressionDoc.docx", saveOptions);
```

Dies sind einige der wichtigsten Optionen und Einstellungen, die Sie beim Speichern von Dokumenten im OOXML-Format mit Aspose.Words für Java verwenden können. Entdecken Sie gerne weitere Optionen und passen Sie Ihren Prozess zum Speichern von Dokumenten nach Bedarf an.

## Vollständiger Quellcode zum Speichern von Dokumenten im OOXML-Format in Aspose.Words für Java

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

## Abschluss

In dieser umfassenden Anleitung haben wir untersucht, wie Sie Dokumente im OOXML-Format mit Aspose.Words für Java speichern. Ganz gleich, ob Sie Ihre Dokumente mit Passwörtern verschlüsseln, die Einhaltung bestimmter OOXML-Standards sicherstellen, Dokumenteigenschaften aktualisieren, alte Steuerzeichen beibehalten oder Komprimierungsstufen anpassen müssen – Aspose.Words bietet einen vielseitigen Satz an Tools, die Ihren Anforderungen gerecht werden.

## FAQs

### Wie entferne ich den Passwortschutz von einem passwortgeschützten Dokument?

Um den Passwortschutz von einem passwortgeschützten Dokument zu entfernen, können Sie das Dokument mit dem richtigen Passwort öffnen und es dann speichern, ohne in den Speicheroptionen ein Passwort anzugeben. Dadurch wird das Dokument ohne Passwortschutz gespeichert.

### Kann ich beim Speichern eines Dokuments im OOXML-Format benutzerdefinierte Eigenschaften festlegen?

 Ja, Sie können benutzerdefinierte Eigenschaften für ein Dokument festlegen, bevor Sie es im OOXML-Format speichern. Benutzen Sie die`BuiltInDocumentProperties` Und`CustomDocumentProperties` Klassen zum Festlegen verschiedener Eigenschaften wie Autor, Titel, Schlüsselwörter und benutzerdefinierte Eigenschaften.

### Was ist die Standardkomprimierungsstufe beim Speichern eines Dokuments im OOXML-Format?

 Die Standardkomprimierungsstufe beim Speichern eines Dokuments im OOXML-Format mit Aspose.Words für Java ist`NORMAL` . Sie können die Komprimierungsstufe ändern`SUPER_FAST` oder`MAXIMUM` wie benötigt.