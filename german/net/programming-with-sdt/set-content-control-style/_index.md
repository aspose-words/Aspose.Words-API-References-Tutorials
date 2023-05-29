---
title: Legen Sie den Stil der Inhaltssteuerung fest
linktitle: Legen Sie den Stil der Inhaltssteuerung fest
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Stil eines Inhaltssteuerelements in einem Word-Dokument festlegen und dabei eine einheitliche Formatierung anwenden.
type: docs
weight: 10
url: /de/net/programming-with-sdt/set-content-control-style/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET den Stil eines Inhaltssteuerelements in einem Word-Dokument festlegen. Für eine einheitliche Formatierung können Sie vordefinierte oder benutzerdefinierte Stile auf Inhaltssteuerelemente anwenden.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und der Arbeit mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und rufen Sie die Inhaltskontrolle ab
 Laden Sie das Word-Dokument mit`Document` Konstruktor, der den Pfad zum Dokument als Parameter übergibt. Rufen Sie das gewünschte Inhaltssteuerelement aus dem Dokument ab. In diesem Beispiel gehen wir davon aus, dass das Inhaltssteuerelement das erste strukturierte Dokument-Tag im Dokument ist.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Schritt 3: Rufen Sie den Stil ab und wenden Sie ihn auf die Inhaltssteuerung an
 Rufen Sie den gewünschten Stil aus der Stilsammlung des Dokuments ab. In diesem Beispiel rufen wir den Stil „Zitat“ mithilfe von ab`StyleIdentifier.Quote` . Weisen Sie dann den abgerufenen Stil dem zu`Style` Eigenschaft des strukturierten Dokument-Tags.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.SetContentControlStyle.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Beispielquellcode für „Set Content Control Style“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Das ist es! Sie haben den Stil eines Inhaltssteuerelements in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich festgelegt.