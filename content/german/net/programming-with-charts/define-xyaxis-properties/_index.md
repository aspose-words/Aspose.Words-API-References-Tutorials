---
title: Definieren Sie die Eigenschaften der XY-Achse in einem Diagramm
linktitle: Definieren Sie die Eigenschaften der XY-Achse in einem Diagramm
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET XY-Achseneigenschaften in einem Diagramm definieren. Anpassungsmöglichkeiten für die X- und Y-Achse werden demonstriert.
type: docs
weight: 10
url: /de/net/programming-with-charts/define-xyaxis-properties/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET Eigenschaften für die X- und Y-Achsen in einem Diagramm definieren. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Achseneigenschaften anpassen.

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

 Fügen Sie als Nächstes mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Flächendiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Reihendaten hinzu

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
	xAxis.CrossesAt = 3; //Gemessen in Anzeigeeinheiten der Y-Achse (Hunderter).
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

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET Eigenschaften für die X- und Y-Achsen in einem Diagramm definieren. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Achseneigenschaften an Ihre spezifischen Anforderungen anpassen. Aspose.Words für .NET bietet eine umfassende API für die Textverarbeitung mit Diagrammen in Word-Dokumenten, sodass Sie verschiedene Aspekte des Diagramms, einschließlich der Achsen, bearbeiten können.

Durch den Zugriff auf`ChartAxis` Bei Objekten, die mit dem Diagramm verknüpft sind, können Sie Eigenschaften wie den Kategorietyp, Achsenkreuze, Teilstriche, Beschriftungspositionen, Skalierung und mehr ändern. Diese Flexibilität ermöglicht es Ihnen, das Erscheinungsbild und Verhalten der Diagrammachsen anzupassen, um Ihre Daten effektiv darzustellen.

Durch die Verwendung von Aspose.Words für .NET können Sie Diagrammerstellungs- und Anpassungsfunktionen nahtlos in Ihre .NET-Anwendungen integrieren und die Erstellung professionell aussehender Dokumente mit umfassenden Visualisierungen automatisieren.

### FAQs

#### Q1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Dokumentverarbeitungsbibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert in .NET-Anwendungen zu erstellen, zu bearbeiten und zu speichern. Es bietet zahlreiche Funktionen für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen.

#### Q2. Wie kann ich Aspose.Words für .NET installieren?
Sie können Aspose.Words für .NET installieren, indem Sie es mithilfe des NuGet-Paketmanagers in Visual Studio herunterladen. Suchen Sie einfach im NuGet-Paketmanager nach „Aspose.Words“ und installieren Sie es in Ihrem Projekt.

#### Q3. Kann ich andere Aspekte des Diagramms mit Aspose.Words für .NET anpassen?
Ja, Aspose.Words für .NET bietet umfangreiche Funktionen zum Anpassen verschiedener Aspekte eines Diagramms. Zusätzlich zum Definieren von Achseneigenschaften können Sie Diagrammtyp, Datenreihen, Legende, Titel, Plotbereich, Datenbeschriftungen und viele andere Elemente des Diagramms ändern. Die API bietet eine detaillierte Kontrolle über die Darstellung und das Verhalten von Diagrammen.

#### Q4. Kann ich mit Aspose.Words für .NET verschiedene Arten von Diagrammen erstellen?
 Ja, Aspose.Words für .NET unterstützt eine Vielzahl von Diagrammtypen, darunter Flächen-, Balken-, Linien-, Kreis-, Streudiagramme und mehr. Du kannst den ... benutzen`ChartType` Aufzählung zur Angabe des gewünschten Diagrammtyps beim Einfügen einer Diagrammform in ein Word-Dokument.

#### F5. Kann ich das Diagramm in verschiedenen Formaten speichern?
Ja, mit Aspose.Words für .NET können Sie das Dokument mit dem Diagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr speichern. Sie können je nach Ihren Anforderungen das passende Format auswählen und nutzen`Save` Methode der`Document` Objekt zum Speichern des Dokuments.

#### F6. Kann ich diese Techniken auf mehrere Diagramme in einem Dokument anwenden?
 Ja, Sie können diese Techniken auf mehrere Diagramme in einem Dokument anwenden, indem Sie die erforderlichen Schritte für jedes Diagramm wiederholen. Sie können separat erstellen`Chart` Und`ChartAxis` Objekte für jedes Diagramm erstellen und deren Eigenschaften entsprechend anpassen. Aspose.Words für .NET bietet vollständige Unterstützung für die Textverarbeitung mit mehreren Diagrammen in einem einzigen Dokument.