---
title: Kontrollkästchentyp-Inhaltssteuerung
linktitle: Kontrollkästchentyp-Inhaltssteuerung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Inhaltssteuerelement vom Typ Kontrollkästchen in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/check-box-type-content-control/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Inhaltssteuerelement vom Typ „Kontrollkästchen“ in einem Word-Dokument erstellen. Mit Kontrollkästcheninhaltssteuerelementen können Benutzer ein Kontrollkästchen innerhalb des Dokuments aktivieren oder deaktivieren.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und einen DocumentBuilder
 Erstellen Sie eine neue Instanz von`Document` Klasse und a`DocumentBuilder` um den Inhalt des Dokuments zu erstellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Fügen Sie ein Inhaltssteuerelement vom Typ Kontrollkästchen hinzu
 Ein ... kreieren`StructuredDocumentTag` mit`SdtType.Checkbox` um das Kontrollkästchen-Inhaltssteuerelement darzustellen. Angeben`MarkupLevel.Inline` um es im Text zu platzieren.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.CheckBoxTypeContentControl.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Beispielquellcode für die Inhaltssteuerung vom Typ „Kontrollkästchen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Inhaltssteuerelement vom Typ „Kontrollkästchen“ in Ihrem Word-Dokument erstellt.