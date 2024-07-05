---
title: Mehrfachabschnitt
linktitle: Mehrfachabschnitt
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET strukturierte Dokument-Tags mit mehreren Abschnitten in einem Word-Dokument abrufen und verarbeiten.
type: docs
weight: 10
url: /de/net/programming-with-sdt/multi-section/
---

In diesem Tutorial wird erklärt, wie Sie mit mehrteiligen strukturierten Dokument-Tags in einem Word-Dokument mithilfe von Aspose.Words für .NET arbeiten. Sie können die im Dokument vorhandenen Abschnitt-Tags abrufen und verarbeiten.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und rufen Sie Tags mit mehreren Abschnitten ab
 Laden Sie das Word-Dokument mit dem`Document` Konstruktor, wobei der Pfad zum Dokument als Parameter übergeben wird. Rufen Sie alle strukturierten Dokument-Tagbereich-Startknoten im Dokument mithilfe des`GetChildNodes` Methode.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Schritt 3: Verarbeiten Sie die Tags mit mehreren Abschnitten
Durchlaufen Sie die Sammlung strukturierter Startknoten für den Tagbereich des Dokuments. In diesem Beispiel drucken wir einfach den Titel jedes Tags auf der Konsole aus. Sie können je nach Bedarf weitere Verarbeitungen durchführen.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Beispielquellcode für Multi Section mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich mehrteilige strukturierte Dokument-Tags in Ihrem Word-Dokument abgerufen und verarbeitet.