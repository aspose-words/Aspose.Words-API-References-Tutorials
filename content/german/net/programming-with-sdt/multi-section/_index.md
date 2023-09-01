---
title: Mehrteilig
linktitle: Mehrteilig
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET strukturierte Dokument-Tags mit mehreren Abschnitten in einem Word-Dokument abrufen und verarbeiten.
type: docs
weight: 10
url: /de/net/programming-with-sdt/multi-section/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET mit strukturierten Dokument-Tags mit mehreren Abschnitten in einem Word-Dokument arbeiten. Sie können die im Dokument vorhandenen Abschnitts-Tags abrufen und verarbeiten.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und rufen Sie Tags mit mehreren Abschnitten ab
 Laden Sie das Word-Dokument mit`Document` Konstruktor, der den Pfad zum Dokument als Parameter übergibt. Rufen Sie alle Startknoten des strukturierten Dokument-Tag-Bereichs im Dokument mit ab`GetChildNodes` Methode.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Schritt 3: Verarbeiten Sie die Multi-Section-Tags
Durchlaufen Sie die Sammlung der Startknoten des strukturierten Dokument-Tag-Bereichs. In diesem Beispiel geben wir einfach den Titel jedes Tags auf der Konsole aus. Sie können die Weiterverarbeitung entsprechend Ihren Anforderungen durchführen.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Beispielquellcode für Multi Section mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich strukturierte Dokument-Tags mit mehreren Abschnitten in Ihrem Word-Dokument abgerufen und verarbeitet.