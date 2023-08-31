---
title: Datums-/Uhrzeitwerte zur Achse eines Diagramms hinzufügen
linktitle: Datums-/Uhrzeitwerte zur Achse eines Diagramms hinzufügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Datums- und Uhrzeitwerte zur Achse eines Diagramms hinzufügen.
type: docs
weight: 10
url: /de/net/programming-with-charts/date-time-values-to-axis/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET Datums- und Uhrzeitwerte zur Achse eines Diagramms hinzufügen.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das Dokument speichern möchten.

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
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.DateTimeValuesToAxis.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Beispielquellcode für Date Time Values To Axis mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET Datums- und Uhrzeitwerte zur Achse eines Diagramms hinzufügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm erstellen, Datums-/Uhrzeitwerte zur Reihe hinzufügen und die Achse so konfigurieren, dass die Datums-/Uhrzeitwerte genau angezeigt werden. Aspose.Words für .NET bietet leistungsstarke Funktionen für die Textverarbeitung mit Diagrammen in Word-Dokumenten, sodass Sie Daten mit Datums- und Zeitwerten effektiv darstellen und visualisieren können.

### FAQs

#### Q1. Kann ich mit Aspose.Words für .NET Datums- und Uhrzeitwerte zur Achse eines Diagramms hinzufügen?
Ja, mit Aspose.Words für .NET können Sie Datums- und Uhrzeitwerte auf der Achse eines Diagramms in einem Word-Dokument hinzufügen und anzeigen. Aspose.Words bietet APIs und Funktionen, um mit verschiedenen Diagrammtypen zu arbeiten und deren Erscheinungsbild anzupassen, einschließlich der Verarbeitung von Datums- und Uhrzeitwerten auf der Achse.

#### Q2. Wie füge ich Datums-/Uhrzeitwerte zur Diagrammreihe hinzu?
 Um der Diagrammreihe Datums-/Uhrzeitwerte hinzuzufügen, können Sie die verwenden`Add`Methode der Diagrammreihe. Geben Sie ein Array von Datums-/Uhrzeitwerten als Kategoriedaten (X-Achse) zusammen mit den entsprechenden Serienwerten an. Dadurch können Sie Datenpunkte mit Datums-/Uhrzeitwerten im Diagramm darstellen.

#### Q3. Wie kann ich die Achse so konfigurieren, dass sie Datums- und Uhrzeitwerte anzeigt?
 Sie können die Achse des Diagramms so konfigurieren, dass Datums- und Uhrzeitwerte angezeigt werden, indem Sie die entsprechenden Eigenschaften festlegen. Beispielsweise können Sie mithilfe von die Mindest- und Höchstwerte für die Achse festlegen`Scaling.Minimum` Und`Scaling.Maximum` Eigenschaften bzw. Darüber hinaus können Sie die Haupt- und Nebeneinheiten festlegen, um das Intervall und die Teilstriche für die Achse zu definieren.
