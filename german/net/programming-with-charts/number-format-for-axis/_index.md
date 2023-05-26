---
title: Zahlenformat für Achse
linktitle: Zahlenformat für Achse
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET das Zahlenformat für eine Achse in einem Diagramm festlegen.
type: docs
weight: 10
url: /de/net/programming-with-charts/number-format-for-axis/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET das Zahlenformat für eine Achse in einem Diagramm festlegen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Achsenbeschriftungen formatieren.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es von der offiziellen Aspose-Website herunterladen oder den NuGet-Paketmanager verwenden, um es zu installieren.
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

## Schritt 3: Fügen Sie dem Diagramm Seriendaten hinzu

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
	// Pfad zu Ihrem Dokumentenverzeichnis
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