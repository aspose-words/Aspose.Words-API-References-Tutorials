---
title: Verwenden von Ladeoptionen in Aspose.Words für Java
linktitle: Verwenden von Ladeoptionen
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Beherrschen der Ladeoptionen in Aspose.Words für Java. Passen Sie das Laden von Dokumenten an, verwalten Sie die Verschlüsselung, konvertieren Sie Formen, legen Sie Word-Versionen fest und mehr für eine effiziente Java-Dokumentverarbeitung.
type: docs
weight: 11
url: /de/java/document-loading-and-saving/using-load-options/
---

## Einführung in die Arbeit mit Ladeoptionen in Aspose.Words für Java

In diesem Tutorial erfahren Sie, wie Sie mit den Ladeoptionen in Aspose.Words für Java arbeiten. Mit den Ladeoptionen können Sie anpassen, wie Dokumente geladen und verarbeitet werden. Wir werden verschiedene Szenarien behandeln, darunter das Aktualisieren schmutziger Felder, das Laden verschlüsselter Dokumente, das Konvertieren von Formen in Office Math, das Festlegen der MS Word-Version, das Angeben eines temporären Ordners, die Behandlung von Warnungen und das Konvertieren von Metadateien in PNG. Lassen Sie uns Schritt für Schritt eintauchen.

## Aktualisieren Sie schmutzige Felder

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

 Dieser Codeausschnitt zeigt, wie fehlerhafte Felder in einem Dokument aktualisiert werden. Der`setUpdateDirtyFields(true)` Die Methode wird verwendet, um sicherzustellen, dass fehlerhafte Felder beim Laden des Dokuments aktualisiert werden.

## Verschlüsseltes Dokument laden

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

 Hier laden wir ein verschlüsseltes Dokument mit einem Passwort. Der`LoadOptions` Der Konstruktor akzeptiert das Dokumentkennwort. Sie können beim Speichern des Dokuments auch ein neues Kennwort angeben`OdtSaveOptions`.

## Konvertieren Sie Shape in Office Math

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
```

 Dieser Code zeigt, wie Formen während des Ladens eines Dokuments in Office Math-Objekte konvertiert werden. Der`setConvertShapeToOfficeMath(true)`-Methode ermöglicht diese Konvertierung.

## Legen Sie die MS Word-Version fest

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

 Sie können die MS Word-Version für das Laden von Dokumenten angeben. In diesem Beispiel stellen wir die Version mit auf Microsoft Word 2010 ein`setMswVersion`.

## Verwenden Sie einen temporären Ordner

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

 Durch Festlegen des temporären Ordners mit`setTempFolder`können Sie steuern, wo temporäre Dateien während der Dokumentenverarbeitung gespeichert werden.

## Achtung, Rückruf

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        // Behandeln Sie Warnungen, sobald sie beim Laden von Dokumenten auftreten.
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

Dieser Code zeigt, wie ein Warnrückruf eingerichtet wird, um Warnungen beim Laden von Dokumenten zu verarbeiten. Sie können das Verhalten Ihrer Anwendung beim Auftreten von Warnungen anpassen.

## Konvertieren Sie Metadateien in PNG

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

 Um Metadateien (z. B. WMF) beim Laden des Dokuments in PNG-Bilder zu konvertieren, können Sie die verwenden`setConvertMetafilesToPng(true)` Methode.

## Vollständiger Quellcode für die Arbeit mit Ladeoptionen in Aspose.Words für Java

```java
public void updateDirtyFields() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setUpdateDirtyFields(true);
	}
	Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
}
@Test
public void loadEncryptedDocument() throws Exception {
	Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
@Test
public void convertShapeToOfficeMath() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertShapeToOfficeMath(true);
	}
	Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
}
@Test
public void setMsWordVersion() throws Exception {
	// Erstellen Sie ein neues LoadOptions-Objekt, das Dokumente standardmäßig gemäß der MS Word 2019-Spezifikation lädt
	// und ändern Sie die Ladeversion auf Microsoft Word 2010.
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setMswVersion(MsWordVersion.WORD_2010);
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
@Test
public void useTempFolder() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setTempFolder("Your Directory Path");
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
@Test
public void warningCallback() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
public static class DocumentLoadingWarningCallback implements IWarningCallback {
	public void warning(WarningInfo info) {
		//Druckt Warnungen und deren Details, sobald sie beim Laden des Dokuments auftreten.
		System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
		System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
	}
}
@Test
public void convertMetafilesToPng() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertMetafilesToPng(true);
	}
	Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
@Test
public void loadChm() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setEncoding(Charset.forName("windows-1251"));
	}
	Document doc = new Document("Your Directory Path" + "HTML help.chm", loadOptions);
}
```

## Abschluss

In diesem Tutorial haben wir uns mit verschiedenen Aspekten der Arbeit mit Ladeoptionen in Aspose.Words für Java befasst. Ladeoptionen spielen eine entscheidende Rolle bei der Anpassung der Art und Weise, wie Dokumente geladen und verarbeitet werden, sodass Sie die Dokumentenverarbeitung an Ihre spezifischen Anforderungen anpassen können. Fassen wir noch einmal die wichtigsten Punkte zusammen, die in diesem Leitfaden behandelt werden:

## FAQs

### Wie kann ich mit Warnungen beim Laden von Dokumenten umgehen?

 Sie können einen Warnrückruf einrichten, wie in der Abbildung gezeigt`warningCallback()` Methode oben. Passen Sie die an`DocumentLoadingWarningCallback` Klasse, um Warnungen entsprechend den Anforderungen Ihrer Anwendung zu behandeln.

### Kann ich beim Laden eines Dokuments Formen in Office Math-Objekte konvertieren?

 Ja, Sie können mithilfe von Formen in Office Math-Objekte konvertieren`loadOptions.setConvertShapeToOfficeMath(true)`.

### Wie lege ich die MS Word-Version für das Laden von Dokumenten fest?

 Verwenden`loadOptions.setMswVersion(MsWordVersion.WORD_2010)` um die MS Word-Version für das Laden von Dokumenten anzugeben.

###  Was ist der Zweck des`setTempFolder` method in Load Options?

 Der`setTempFolder`Mit der Methode können Sie den Ordner angeben, in dem temporäre Dateien während der Dokumentverarbeitung gespeichert werden.