---
title: Inhaltssteuerelement vom Typ „Kontrollkästchen“
linktitle: Inhaltssteuerelement vom Typ „Kontrollkästchen“
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Inhaltssteuerelement vom Typ „Kontrollkästchen“ in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/check-box-type-content-control/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Inhaltssteuerelement vom Typ „Kontrollkästchen“ in einem Word-Dokument erstellen. Mit Inhaltssteuerelementen für Kontrollkästchen können Benutzer ein Kontrollkästchen im Dokument aktivieren oder deaktivieren.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und einen DocumentBuilder
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`DocumentBuilder` um den Inhalt des Dokuments zu erstellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Hinzufügen eines Inhaltssteuerelements vom Typ „Kontrollkästchen“
 Ein ... kreieren`StructuredDocumentTag` mit`SdtType.Checkbox` um das Kontrollkästchen-Inhaltssteuerelement darzustellen. Geben Sie`MarkupLevel.Inline` um es in den Text einzufügen.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.CheckBoxTypeContentControl.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Beispielquellcode für Kontrollkästchen-Inhaltssteuerelement mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Inhaltssteuerelement vom Typ Kontrollkästchen in Ihrem Word-Dokument erstellt.