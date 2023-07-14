---
title: Am Raster ausrichten
linktitle: Am Raster ausrichten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der Snap to Grid-Funktion mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/document-formatting/snap-to-grid/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Funktion „An Raster ausrichten“ mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

## Schritt 1: Dokument erstellen und konfigurieren

Erstellen Sie zunächst ein neues Dokument und ein zugehöriges DocumentBuilder-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Rasterausrichtung

Jetzt wenden wir die Rasterausrichtung auf einen bestimmten Absatz und die im Absatz verwendete Schriftart an. Hier ist wie:

```csharp
// Aktivieren Sie die Rasterausrichtung für den Absatz
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// Schreiben Sie Text in den Absatz
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// Aktivieren Sie die Rasterausrichtung für die im Absatz verwendete Schriftart
par.Runs[0].Font.SnapToGrid = true;
```

## Schritt 3: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### Beispielquellcode für Snap To Grid mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Snap to Grid-Funktion mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Optimieren Sie das Layout bei der Eingabe asiatischer Zeichen.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

Mit diesem Code können Sie Ihren Text am Raster ausrichten und das Erscheinungsbild Ihres Dokuments mithilfe von Aspose.Words für .NET optimieren.

