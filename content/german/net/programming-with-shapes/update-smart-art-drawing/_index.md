---
title: Smart Art-Zeichnung aktualisieren
linktitle: Smart Art-Zeichnung aktualisieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Smart Art-Zeichnung in einem Word-Dokument mit Aspose.Words für .NET aktualisieren.
type: docs
weight: 10
url: /de/net/programming-with-shapes/update-smart-art-drawing/
---

In diesem Tutorial wird erklärt, wie Sie die Smart Art-Zeichnung in einem Word-Dokument mit Aspose.Words für .NET aktualisieren. Indem Sie die Formen im Dokument durchgehen und prüfen, ob sie über Smart Art verfügen, können Sie die Smart Art-Zeichnung aktualisieren, um alle an ihren Daten vorgenommenen Änderungen widerzuspiegeln.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument
 Laden Sie das Word-Dokument, das die Smart Art-Zeichnung enthält, mit dem`Document` Klassenkonstruktor.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Schritt 3: Aktualisieren Sie die Smart Art-Zeichnung
 Iterieren Sie durch die Formen im Dokument mit dem`GetChildNodes` Methode mit dem`NodeType.Shape` Parameter. Überprüfen Sie, ob jede Form Smart Art hat, indem Sie den`HasSmartArt`Eigenschaft, und wenn wahr, rufen Sie die`UpdateSmartArtDrawing` Methode zum Aktualisieren der Smart Art-Zeichnung.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Beispielquellcode zum Aktualisieren von Smart Art Drawing mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Das ist es! Sie haben die Smart Art-Zeichnung in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich aktualisiert.