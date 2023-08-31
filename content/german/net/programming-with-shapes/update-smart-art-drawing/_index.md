---
title: Aktualisieren Sie Smart Art Drawing
linktitle: Aktualisieren Sie Smart Art Drawing
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Smart Art-Zeichnung in einem Word-Dokument mit Aspose.Words für .NET aktualisieren.
type: docs
weight: 10
url: /de/net/programming-with-shapes/update-smart-art-drawing/
---

In diesem Tutorial wird erklärt, wie Sie die Smart Art-Zeichnung in einem Word-Dokument mit Aspose.Words für .NET aktualisieren. Indem Sie die Formen im Dokument durchlaufen und prüfen, ob sie über Smart Art verfügen, können Sie die Smart Art-Zeichnung aktualisieren, um alle an ihren Daten vorgenommenen Änderungen widerzuspiegeln.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument
 Laden Sie das Word-Dokument, das die Smart Art-Zeichnung enthält, mit`Document` Klassenkonstruktor.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Schritt 3: Aktualisieren Sie die Smart Art-Zeichnung
 Durchlaufen Sie die Formen im Dokument mithilfe von`GetChildNodes` Methode mit der`NodeType.Shape` Parameter. Überprüfen Sie mithilfe von, ob jede Form über Smart Art verfügt`HasSmartArt` Eigenschaft, und wenn wahr, nennen Sie die`UpdateSmartArtDrawing` Methode zum Aktualisieren der Smart Art-Zeichnung.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Beispielquellcode für die Aktualisierung von Smart Art Drawing mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Das ist es! Sie haben die Smart Art-Zeichnung in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich aktualisiert.