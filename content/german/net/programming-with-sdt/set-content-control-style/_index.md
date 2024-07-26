---
title: Festlegen des Inhaltssteuerelementstils
linktitle: Festlegen des Inhaltssteuerelementstils
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Stil eines Inhaltssteuerelements in einem Word-Dokument festlegen und dabei eine konsistente Formatierung anwenden.
type: docs
weight: 10
url: /de/net/programming-with-sdt/set-content-control-style/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET den Stil eines Inhaltssteuerelements in einem Word-Dokument festlegen. Sie können vordefinierte oder benutzerdefinierte Stile auf Inhaltssteuerelemente anwenden, um eine konsistente Formatierung zu gewährleisten.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und rufen Sie das Inhaltssteuerelement ab
 Laden Sie das Word-Dokument mit dem`Document`Konstruktor, wobei der Pfad zum Dokument als Parameter übergeben wird. Rufen Sie das gewünschte Inhaltssteuerelement aus dem Dokument ab. In diesem Beispiel gehen wir davon aus, dass das Inhaltssteuerelement das erste strukturierte Dokument-Tag im Dokument ist.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Schritt 3: Abrufen des Stils und Anwenden auf das Inhaltssteuerelement
 Rufen Sie den gewünschten Stil aus der Stilsammlung des Dokuments ab. In diesem Beispiel rufen wir den Stil „Zitat“ ab, indem wir`StyleIdentifier.Quote` . Weisen Sie dann den abgerufenen Stil dem`Style` Eigenschaft des strukturierten Dokument-Tags.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.SetContentControlStyle.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Beispielquellcode für Set Content Control Style mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Das ist es! Sie haben den Stil eines Inhaltssteuerelements in Ihrem Word-Dokument erfolgreich mit Aspose.Words für .NET festgelegt.