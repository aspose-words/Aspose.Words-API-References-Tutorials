---
title: Legen Sie die Farbe der Inhaltssteuerung fest
linktitle: Legen Sie die Farbe der Inhaltssteuerung fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Farbe eines Inhaltssteuerelements in einem Word-Dokument festlegen und dessen Erscheinungsbild anpassen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/set-content-control-color/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Farbe eines Inhaltssteuerelements in einem Word-Dokument festlegen. Sie können das Erscheinungsbild von Inhaltssteuerelementen anpassen, indem Sie deren Farbe ändern.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und rufen Sie die Inhaltssteuerung ab
 Laden Sie das Word-Dokument mit`Document` Konstruktor, der den Pfad zum Dokument als Parameter übergibt. Rufen Sie das gewünschte Inhaltssteuerelement aus dem Dokument ab. In diesem Beispiel gehen wir davon aus, dass das Inhaltssteuerelement das erste strukturierte Dokument-Tag im Dokument ist.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Schritt 3: Legen Sie die Inhaltskontrollfarbe fest
 Legen Sie die Farbe des Inhaltssteuerelements fest, indem Sie a zuweisen`Color` Wert für die`Color` Eigenschaft des strukturierten Dokument-Tags. In diesem Beispiel stellen wir die Farbe auf Rot ein.

```csharp
sdt.Color = Color.Red;
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.SetContentControlColor.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Beispielquellcode für „Set Content Control Color“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Das ist es! Sie haben die Farbe eines Inhaltssteuerelements in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich festgelegt.