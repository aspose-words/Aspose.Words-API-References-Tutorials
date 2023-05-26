---
title: Definieren Sie XYAxis-Eigenschaften
linktitle: Definieren Sie XYAxis-Eigenschaften
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET XY-Achseneigenschaften in einem Diagramm definieren. Anpassungsmöglichkeiten für die X- und Y-Achse werden demonstriert.
type: docs
weight: 10
url: /de/net/programming-with-charts/define-xyaxis-properties/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET Eigenschaften für die X- und Y-Achsen in einem Diagramm definieren. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Achseneigenschaften anpassen.

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

 Fügen Sie als Nächstes mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Flächendiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Seriendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir fünf Datenpunkte mit entsprechenden Daten und Werten hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## Schritt 4: Passen Sie die Eigenschaften der X- und Y-Achse an

 Um die Eigenschaften der X- und Y-Achse anzupassen, greifen Sie auf zu`ChartAxis` Objekte, die mit dem Diagramm verknüpft sind.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Ändern Sie die Eigenschaften von`xAxis` Und`yAxis`Objekte, um die gewünschten Optionen für die X- und Y-Achse festzulegen. In diesem Beispiel demonstrieren wir einige allgemeine Eigenschaften, die angepasst werden können.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Damit ist die Implementierung der Definition von XY-Achseneigenschaften in einem Diagramm mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Definieren von XYAxis-Eigenschaften mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Diagramm einfügen
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Ändern Sie die X-Achse in „Kategorie“ statt „Datum“, sodass alle Punkte im gleichen Abstand auf der X-Achse platziert werden.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; // Gemessen in Anzeigeeinheiten der Y-Achse (Hunderter).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```