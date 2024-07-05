---
title: Zahlenformat für Achsen in einem Diagramm
linktitle: Zahlenformat für Achsen in einem Diagramm
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET das Zahlenformat für eine Achse in einem Diagramm festlegen.
type: docs
weight: 10
url: /de/net/programming-with-charts/number-format-for-axis/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET das Zahlenformat für eine Achse in einem Diagramm festlegen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und die Achsenbeschriftungen formatieren.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Words für die .NET-Bibliothek installiert. Sie können sie mit dem NuGet-Paketmanager herunterladen und installieren.
- Ein Dokumentverzeichnispfad, in dem das Ausgabedokument gespeichert wird.

## Schritt 2: Neues Dokument erstellen und Diagramm einfügen

 Erstelle eine neue`Document` Objekt und ein`DocumentBuilder` um das Dokument zu erstellen.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Verwenden Sie als nächstes die`InsertChart` Methode der`DocumentBuilder` , um ein Säulendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Seriendaten zum Diagramm hinzufügen

Fügen Sie dem Diagramm Reihendaten hinzu. In diesem Beispiel fügen wir fünf Elemente mit den entsprechenden Werten hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Schritt 4: Formatieren Sie die Achsenbeschriftungen

 Um das Zahlenformat für die Y-Achsenbeschriftungen festzulegen, rufen Sie das`AxisY` des Diagramms und legen Sie die`NumberFormat.FormatCode` -Eigenschaft auf das gewünschte Format. In diesem Beispiel setzen wir das Format auf „#,##0“, um Zahlen mit Tausendertrennzeichen anzuzeigen.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Damit ist die Implementierung der Festlegung des Zahlenformats für die Achse mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für das Zahlenformat für Achsen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET das Zahlenformat für eine Achse in einem Diagramm festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Säulendiagramm einfügen, Reihendaten hinzufügen und die Achsenbeschriftungen so formatieren, dass Zahlen in einem bestimmten Format angezeigt werden.

Aspose.Words für .NET bietet leistungsstarke Funktionen zum Anpassen des Erscheinungsbilds von Diagrammen in Word-Dokumenten. Durch Festlegen des Zahlenformats für die Achsenbeschriftungen können Sie steuern, wie Zahlen angezeigt werden, einschließlich Optionen wie Dezimalstellen, Tausendertrennzeichen, Währungssymbole und mehr. Auf diese Weise können Sie numerische Daten klar und aussagekräftig darstellen.

Mit Aspose.Words für .NET haben Sie die Flexibilität, verschiedene Aspekte des Diagramms zu formatieren, einschließlich der Achsenbeschriftungen. Indem Sie das Zahlenformat für die Achse festlegen, können Sie Konsistenz sicherstellen und die Lesbarkeit des Diagramms verbessern, sodass Benutzer die dargestellten Werte leichter interpretieren können.

### FAQs

#### F1. Was ist das Zahlenformat für eine Achse in einem Diagramm?
Das Zahlenformat für eine Achse in einem Diagramm bezieht sich auf die Formatierung, die auf die auf der Achse angezeigten numerischen Werte angewendet wird. Sie können damit steuern, wie Zahlen dargestellt werden, einschließlich Optionen wie Dezimalstellen, Tausendertrennzeichen, Währungssymbole, Prozentzeichen und mehr. Durch Festlegen des Zahlenformats können Sie das Erscheinungsbild numerischer Daten im Diagramm an Ihre spezifischen Anforderungen anpassen.

#### F2. Wie kann ich das Zahlenformat für die Achsenbeschriftungen festlegen?
 Um das Zahlenformat für die Achsenbeschriftungen in einem Diagramm mit Aspose.Words für .NET festzulegen, können Sie auf die`AxisY` des Diagramms und legen Sie die`NumberFormat.FormatCode`-Eigenschaft auf den gewünschten Formatcode. Der Formatcode folgt der Syntax standardmäßiger numerischer Formatierungsmuster und bestimmt, wie die Zahlen angezeigt werden. Sie können beispielsweise „#,##0.00“ verwenden, um Zahlen mit zwei Dezimalstellen und Tausendertrennzeichen anzuzeigen.

#### F3. Kann ich unterschiedliche Zahlenformate für die Beschriftungen der X- und Y-Achse festlegen?
Ja, Sie können mit Aspose.Words für .NET unterschiedliche Zahlenformate für die Beschriftungen der X- und Y-Achse festlegen. Greifen Sie auf die jeweilige Achse zu (`AxisX` für X-Achse oder`AxisY` für die Y-Achse) des Diagramms und ändern Sie die`NumberFormat.FormatCode` -Eigenschaft für jede Achse einzeln festlegen. So können Sie den Beschriftungen auf jeder Achse je nach Ihren spezifischen Anforderungen unterschiedliche Zahlenformate zuweisen.

#### F4. Welche gängigen Zahlenformatcodes kann ich verwenden?
Aspose.Words für .NET unterstützt eine Vielzahl von Zahlenformatcodes, die Sie zum Formatieren der Achsenbeschriftungen in einem Diagramm verwenden können. Einige gängige Formatcodes sind:

- `0` oder`#` - Zeigt die Zahl ohne Dezimalstellen an.
- `0.00` oder`#.00` - Zeigt die Zahl mit zwei Dezimalstellen an.
- `#,##0` Zeigt die Zahl mit Tausendertrennzeichen an.
- `"€"0.00` - Zeigt die Zahl mit dem Euro-Währungssymbol und zwei Dezimalstellen an.
- `"%"0` - Zeigt die Zahl als Prozentsatz an.

 Weitere Informationen zur Nummer finden Sie[Formatcodes](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) in der API-Referenz von Aspose.Words für .NET.

#### F5. Kann ich andere Eigenschaften der Achsenbeschriftungen anpassen?
Ja, Aspose.Words für .NET bietet eine breite Palette von Eigenschaften, um das Erscheinungsbild und Verhalten von Achsenbeschriftungen anzupassen. Zusätzlich zum Zahlenformat können Sie Eigenschaften wie Schriftart, Größe, Farbe, Ausrichtung, Ausrichtung und mehr ändern. Auf diese Weise können Sie die Achsenbeschriftungen vollständig an Ihren gewünschten Stil und Ihre Präsentationsanforderungen anpassen.