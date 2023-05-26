---
title: Datum-Uhrzeit-Werte zur Achse
linktitle: Datum-Uhrzeit-Werte zur Achse
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Datums- und Uhrzeitwerte zur Achse eines Diagramms hinzufügen.
type: docs
weight: 10
url: /de/net/programming-with-charts/date-time-values-to-axis/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET Datums- und Uhrzeitwerte zur Achse eines Diagramms hinzufügen.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und der Arbeit mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"`mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
 Erstellen Sie eine neue Instanz von`Document` Klasse und a`DocumentBuilder` Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Fügen Sie eine Diagrammform ein und konfigurieren Sie sie
 Fügen Sie mithilfe von eine Diagrammform in das Dokument ein`InsertChart` Methode der`DocumentBuilder` Objekt. Legen Sie den gewünschten Diagrammtyp und die gewünschten Abmessungen fest.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Schritt 4: Daten zum Diagramm hinzufügen
Fügen Sie der Diagrammreihe Daten hinzu, einschließlich Datums- und Uhrzeitwerten.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Schritt 5: Konfigurieren Sie die Achse
Konfigurieren Sie die X-Achse des Diagramms für die Anzeige der Datums- und Uhrzeitwerte.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Schritt 6: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.DateTimeValuesToAxis.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Beispielquellcode für Date Time Values To Axis mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Legen Sie die Haupteinheiten auf eine Woche und die Nebeneinheiten auf einen Tag fest.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Dieser Beispielcode erstellt ein neues Word-Dokument, fügt ein Säulendiagramm mit Datums-/Uhrzeitwerten auf der X-Achse ein und speichert das Dokument im angegebenen Verzeichnis.