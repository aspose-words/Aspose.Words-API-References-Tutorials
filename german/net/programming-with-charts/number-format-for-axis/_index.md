---
title: Zahlenformat für Achsen in einem Diagramm
linktitle: Zahlenformat für Achsen in einem Diagramm
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET das Zahlenformat für eine Achse in einem Diagramm festlegen.
type: docs
weight: 10
url: /de/net/programming-with-charts/number-format-for-axis/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET das Zahlenformat für eine Achse in einem Diagramm festlegen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Achsenbeschriftungen formatieren.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen, indem Sie es mit dem NuGet-Paketmanager installieren.
- Ein Dokumentverzeichnispfad, in dem das Ausgabedokument gespeichert wird.

## Schritt 2: Erstellen Sie ein neues Dokument und fügen Sie ein Diagramm ein

 Erstelle eine neue`Document` Objekt und a`DocumentBuilder` um das Dokument zu erstellen.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Als nächstes verwenden Sie die`InsertChart` Methode der`DocumentBuilder` um ein Säulendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Reihendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir fünf Elemente mit ihren entsprechenden Werten hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Schritt 4: Formatieren Sie die Achsenbeschriftungen

 Um das Zahlenformat für die Y-Achsenbeschriftungen festzulegen, greifen Sie auf zu`AxisY` Eigenschaft des Diagramms und legen Sie fest`NumberFormat.FormatCode` Eigenschaft in das gewünschte Format. In diesem Beispiel legen wir das Format auf „#,##0“ fest, um Zahlen mit Tausendertrennzeichen anzuzeigen.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Damit ist die Implementierung des Festlegens des Zahlenformats für die Achse mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für das Zahlenformat für Achsen mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET das Zahlenformat für eine Achse in einem Diagramm festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Säulendiagramm einfügen, Reihendaten hinzufügen und die Achsenbeschriftungen formatieren, um Zahlen in einem bestimmten Format anzuzeigen.

Aspose.Words für .NET bietet leistungsstarke Funktionen zum Anpassen der Darstellung von Diagrammen in Word-Dokumenten. Durch Festlegen des Zahlenformats für die Achsenbeschriftungen können Sie steuern, wie Zahlen angezeigt werden, einschließlich Optionen wie Dezimalstellen, Tausendertrennzeichen, Währungssymbole und mehr. Dadurch können Sie numerische Daten übersichtlich und aussagekräftig darstellen.

Mit Aspose.Words für .NET haben Sie die Flexibilität, verschiedene Aspekte des Diagramms, einschließlich der Achsenbeschriftungen, zu formatieren. Durch Festlegen des Zahlenformats für die Achse können Sie Konsistenz gewährleisten und die Lesbarkeit des Diagramms verbessern, sodass Benutzer die dargestellten Werte leichter interpretieren können.

### FAQs

#### Q1. Was ist das Zahlenformat für eine Achse in einem Diagramm?
Das Zahlenformat für eine Achse in einem Diagramm bezieht sich auf die Formatierung, die auf die auf der Achse angezeigten numerischen Werte angewendet wird. Sie können damit steuern, wie Zahlen dargestellt werden, einschließlich Optionen wie Dezimalstellen, Tausendertrennzeichen, Währungssymbole, Prozentzeichen und mehr. Durch Festlegen des Zahlenformats können Sie die Darstellung numerischer Daten im Diagramm an Ihre spezifischen Anforderungen anpassen.

#### Q2. Wie kann ich das Zahlenformat für die Achsenbeschriftungen festlegen?
 Um das Zahlenformat für die Achsenbeschriftungen in einem Diagramm mit Aspose.Words für .NET festzulegen, können Sie auf Folgendes zugreifen:`AxisY` Eigenschaft des Diagramms und legen Sie fest`NumberFormat.FormatCode`Eigenschaft dem gewünschten Formatcode zu. Der Formatcode folgt der Syntax standardmäßiger numerischer Formatierungsmuster und bestimmt, wie die Zahlen angezeigt werden. Beispielsweise können Sie „#,##0.00“ verwenden, um Zahlen mit zwei Dezimalstellen und Tausendertrennzeichen anzuzeigen.

#### Q3. Kann ich unterschiedliche Zahlenformate für die Beschriftungen der X- und Y-Achse festlegen?
Ja, Sie können mit Aspose.Words für .NET unterschiedliche Zahlenformate für die Beschriftungen der X- und Y-Achse festlegen. Greifen Sie auf die entsprechende Achse zu (`AxisX` für X-Achse bzw`AxisY` für die Y-Achse) des Diagramms und ändern Sie die`NumberFormat.FormatCode` Eigenschaft einzeln für jede Achse festlegen. Dadurch können Sie je nach Ihren spezifischen Anforderungen unterschiedliche Zahlenformate auf die Beschriftungen auf jeder Achse anwenden.

#### Q4. Welche gängigen Zahlenformatcodes kann ich verwenden?
Aspose.Words für .NET unterstützt eine Vielzahl von Zahlenformatcodes, die Sie zum Formatieren der Achsenbeschriftungen in einem Diagramm verwenden können. Zu den gängigen Formatcodes gehören:

- `0` oder`#` - Zeigt die Zahl ohne Dezimalstellen an.
- `0.00` oder`#.00` - Zeigt die Zahl mit zwei Dezimalstellen an.
- `#,##0` Zeigt die Zahl mit Tausendertrennzeichen an.
- `"€"0.00` - Zeigt die Zahl mit dem Euro-Währungssymbol und zwei Dezimalstellen an.
- `"%"0` - Zeigt die Zahl als Prozentsatz an.

 Weitere Informationen zur Nummer finden Sie hier[Formatcodes](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) in der API-Referenz von Aspose.Words für .NET.

#### F5. Kann ich andere Eigenschaften der Achsenbeschriftungen anpassen?
Ja, Aspose.Words für .NET bietet eine breite Palette von Eigenschaften, um das Erscheinungsbild und Verhalten von Achsenbeschriftungen anzupassen. Zusätzlich zum Zahlenformat können Sie Eigenschaften wie Schriftart, Größe, Farbe, Ausrichtung, Ausrichtung und mehr ändern. Dadurch können Sie die Achsenbeschriftungen vollständig an Ihren gewünschten Stil und Ihre Präsentationsanforderungen anpassen.