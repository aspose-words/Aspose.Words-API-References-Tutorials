---
title: Wenden Sie Rahmen und Schattierungen auf Absätze in Word-Dokumenten an
linktitle: Wenden Sie Rahmen und Schattierungen auf Absätze in Word-Dokumenten an
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Rahmen und Schattierungen auf einen Absatz in einem Word-Dokument anwenden.
type: docs
weight: 10
url: /de/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mithilfe der Funktionalität von Aspose.Words für .NET Rahmen und Schattierungen auf einen Absatz in einem Word-Dokument anwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und Formatierungsänderungen anzuwenden.

## Schritt 1: Dokument erstellen und konfigurieren

Erstellen Sie zunächst ein neues Dokument und ein zugehöriges DocumentBuilder-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Randkonfiguration

Jetzt konfigurieren wir die Absatzränder, indem wir den Rahmenstil für jede Seite festlegen. Hier ist wie:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Schritt 3: Einrichten der Füllung

Wir konfigurieren nun die Absatzfüllung, indem wir die Textur und die Füllfarben festlegen. Hier ist wie:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Schritt 4: Inhalte hinzufügen

Wir werden dem Absatz formatierten Inhalt hinzufügen. Hier ist wie:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Schritt 3: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Beispielquellcode für „Rahmen und Schattierung auf Absatz anwenden“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Rahmen und Schattierung auf Absatz anwenden“ mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Abschluss

 In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Rahmen und Schattierungen auf einen Absatz in einem Word-Dokument anwendet. Durch die Konfiguration der Absätze`Borders` Und`Shading` Eigenschaften konnten wir den Rahmenstil, die Linienfarbe und die Füllfarbe für den Absatz festlegen. Aspose.Words für .NET bietet leistungsstarke Formatierungsfunktionen, um das Erscheinungsbild von Absätzen anzupassen und die visuelle Darstellung Ihrer Dokumente zu verbessern.

### FAQs

#### F: Wie wende ich mit Aspose.Words für .NET Rahmen und Schattierungen auf einen Absatz in einem Word-Dokument an?

A: Um mit Aspose.Words für .NET Rahmen und Schattierungen auf einen Absatz in einem Word-Dokument anzuwenden, führen Sie die folgenden Schritte aus:
1.  Erstellen Sie ein neues Dokument und a`DocumentBuilder` Objekt.
2.  Konfigurieren Sie die Absatzränder, indem Sie auf zugreifen`Borders` Eigentum der`ParagraphFormat` und Festlegen des Rahmenstils für jede Seite.
3. Konfigurieren Sie die Absatzfüllung, indem Sie auf zugreifen`Shading` Eigentum der`ParagraphFormat` und Festlegen der Textur- und Füllfarben.
4.  Fügen Sie dem Absatz Inhalte hinzu, indem Sie verwenden`Write` Methode der`DocumentBuilder`.
5.  Speichern Sie das Dokument mit`Save` Methode.

#### F: Wie stelle ich den Rahmenstil für jede Seite des Absatzes ein?

 A: Um den Rahmenstil für jede Seite des Absatzes festzulegen, können Sie auf zugreifen`Borders` Eigentum der`ParagraphFormat` und stellen Sie die ein`LineStyle` Eigentum für jeden`BorderType` (z.B.,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Sie können verschiedene Linienstile angeben, z`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, usw.

#### F: Wie lege ich die Textur- und Füllfarben für die Absatzschattierung fest?

 A: Um die Textur und Füllfarben für die Absatzschattierung festzulegen, können Sie auf zugreifen`Shading` Eigentum der`ParagraphFormat` und stellen Sie die ein`Texture` Eigenschaft zu einem gewünschten Texturindex (z. B.`TextureIndex.TextureDiagonalCross` ). Sie können auch die festlegen`BackgroundPatternColor` Und`ForegroundPatternColor` Eigenschaften zu den gewünschten Farben mithilfe der`System.Drawing.Color` Klasse.