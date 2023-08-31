---
title: Am Raster im Word-Dokument ausrichten
linktitle: Am Raster im Word-Dokument ausrichten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der Snap to Grid-Funktion in Word-Dokumenten mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/document-formatting/snap-to-grid/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie die Funktion „Am Raster ausrichten“ in Word-Dokumenten mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

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


## Abschluss

In diesem Tutorial haben wir den Prozess der Verwendung der Funktion „Am Raster ausrichten“ in einem Word-Dokument mit Aspose.Words für .NET untersucht. Indem Sie die beschriebenen Schritte befolgen, können Sie die Rasterausrichtung für Absätze und Schriftarten aktivieren und so ein optisch ansprechendes und gut organisiertes Dokumentlayout gewährleisten.

### FAQs

#### F: Was ist „Am Raster ausrichten“ in einem Word-Dokument?

A: Am Raster ausrichten ist eine Funktion in Word-Dokumenten, die Objekte wie Text und Bilder an einem Rastersystem ausrichtet. Dies gewährleistet eine präzise Positionierung und saubere Ausrichtung, was besonders hilfreich ist, wenn es um komplexe Layouts oder asiatische Zeichen geht.

#### F: Wie verbessert Snap to Grid das Erscheinungsbild eines Dokuments?

A: „Am Raster ausrichten“ verbessert das Erscheinungsbild eines Dokuments, indem die konsistente Ausrichtung von Objekten beibehalten wird. Es verhindert, dass Text und andere Elemente falsch ausgerichtet oder überlappend erscheinen, was zu einem professionellen und ausgefeilten Layout führt.

#### F: Kann ich „Am Raster ausrichten“ auf bestimmte Absätze oder Schriftarten in meinem Dokument anwenden?

 A: Ja, Sie können „Am Raster ausrichten“ auf bestimmte Absätze oder Schriftarten in Ihrem Dokument anwenden. Durch die Aktivierung des`ParagraphFormat.SnapToGrid` Und`Font.SnapToGrid` Mit den Eigenschaften können Sie die Rasterausrichtung pro Absatz oder pro Schriftart steuern.

#### F: Ist Aspose.Words für .NET die einzige Lösung für Snap to Grid in Word-Dokumenten?

A: Aspose.Words für .NET ist eine der verfügbaren Lösungen für die Implementierung von Snap to Grid in Word-Dokumenten. Es gibt andere Methoden und Tools, aber Aspose.Words für .NET bietet robuste APIs und Funktionen für die programmgesteuerte Arbeit mit Word-Dokumenten.

#### F: Kann ich Aspose.Words für .NET verwenden, um mit anderen Dokumentfunktionen zu arbeiten?

A: Ja, Aspose.Words für .NET bietet zahlreiche Funktionen für die Arbeit mit Word-Dokumenten. Es umfasst Funktionen zur Textbearbeitung, zum Seitenlayout, zu Tabellen, Bildern und mehr. Sie können Word-Dokumente mit Aspose.Words für .NET erstellen, ändern und konvertieren.
