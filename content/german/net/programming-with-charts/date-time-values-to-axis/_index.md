---
title: Hinzufügen von Datums- und Uhrzeitwerten zu den Achsen eines Diagramms
linktitle: Hinzufügen von Datums- und Uhrzeitwerten zu den Achsen eines Diagramms
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Datums- und Uhrzeitwerte zur Achse eines Diagramms hinzufügen.
type: docs
weight: 10
url: /de/net/programming-with-charts/date-time-values-to-axis/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET Datums- und Uhrzeitwerte zur Achse eines Diagramms hinzufügen.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Neues Dokument und DocumentBuilder erstellen
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`DocumentBuilder`Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen und Konfigurieren einer Diagrammform
 Fügen Sie eine Diagrammform in das Dokument ein, indem Sie das`InsertChart` Methode der`DocumentBuilder` Objekt. Legen Sie den gewünschten Diagrammtyp und die gewünschten Abmessungen fest.

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
Konfigurieren Sie die X-Achse des Diagramms zur Anzeige der Datums- und Uhrzeitwerte.

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
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.DateTimeValuesToAxis.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Beispielquellcode für Date Time Values To Axis mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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
	// Legen Sie Haupteinheiten auf eine Woche und Nebeneinheiten auf einen Tag fest.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Dieser Beispielcode erstellt ein neues Word-Dokument, fügt ein Säulendiagramm mit Datums- und Uhrzeitwerten auf der X-Achse ein und speichert das Dokument im angegebenen Verzeichnis.

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET Datums- und Uhrzeitwerte zur Achse eines Diagramms hinzufügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm erstellen, der Reihe Datums- und Uhrzeitwerte hinzufügen und die Achse so konfigurieren, dass die Datums- und Uhrzeitwerte genau angezeigt werden. Aspose.Words für .NET bietet einen leistungsstarken Satz von Funktionen für die Textverarbeitung mit Diagrammen in Word-Dokumenten, mit denen Sie Daten mit Datums- und Uhrzeitwerten effektiv darstellen und visualisieren können.

### FAQs

#### F1. Kann ich mit Aspose.Words für .NET Datums- und Zeitwerte zur Achse eines Diagramms hinzufügen?
Ja, mit Aspose.Words für .NET können Sie Datums- und Zeitwerte auf der Achse eines Diagramms in einem Word-Dokument hinzufügen und anzeigen. Aspose.Words bietet APIs und Funktionen, um mit verschiedenen Diagrammtypen zu arbeiten und deren Erscheinungsbild anzupassen, einschließlich der Handhabung von Datums- und Zeitwerten auf der Achse.

#### F2. Wie füge ich der Diagrammreihe Datums- und Zeitwerte hinzu?
 Um Datums- und Zeitwerte zur Diagrammreihe hinzuzufügen, können Sie das`Add`Methode der Diagrammreihe. Stellen Sie ein Array von Datums- und Zeitwerten als Kategoriedaten (X-Achse) zusammen mit den entsprechenden Reihenwerten bereit. Auf diese Weise können Sie Datenpunkte mit Datums- und Zeitwerten im Diagramm darstellen.

#### F3. Wie kann ich die Achse so konfigurieren, dass Datums- und Uhrzeitwerte angezeigt werden?
 Sie können die Achse des Diagramms so konfigurieren, dass Datums- und Zeitwerte angezeigt werden, indem Sie die entsprechenden Eigenschaften festlegen. Sie können beispielsweise die Mindest- und Höchstwerte für die Achse mithilfe der`Scaling.Minimum` Und`Scaling.Maximum` Eigenschaften. Darüber hinaus können Sie die Haupt- und Nebeneinheiten festlegen, um das Intervall und die Teilstriche für die Achse zu definieren.
