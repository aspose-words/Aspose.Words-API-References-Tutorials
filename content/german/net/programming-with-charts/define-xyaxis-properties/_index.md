---
title: Definieren von XY-Achseneigenschaften in einem Diagramm
linktitle: Definieren von XY-Achseneigenschaften in einem Diagramm
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET XY-Achseneigenschaften in einem Diagramm definieren. Anpassungsoptionen für die X- und Y-Achsen werden demonstriert.
type: docs
weight: 10
url: /de/net/programming-with-charts/define-xyaxis-properties/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET Eigenschaften für die X- und Y-Achsen in einem Diagramm definieren. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und die Achseneigenschaften anpassen.

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

 Fügen Sie als nächstes ein Diagramm in das Dokument ein, indem Sie`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Flächendiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Seriendaten zum Diagramm hinzufügen

Fügen Sie dem Diagramm Reihendaten hinzu. In diesem Beispiel fügen wir fünf Datenpunkte mit entsprechenden Daten und Werten hinzu.

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

## Schritt 4: X- und Y-Achseneigenschaften anpassen

 Um die Eigenschaften der X- und Y-Achse anzupassen, rufen Sie die`ChartAxis` Objekte, die mit dem Diagramm verknüpft sind.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Ändern Sie die Eigenschaften des`xAxis` Und`yAxis`Objekte, um die gewünschten Optionen für die X- und Y-Achsen einzustellen. In diesem Beispiel demonstrieren wir einige allgemeine Eigenschaften, die angepasst werden können.

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

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Damit ist die Implementierung der Definition von XY-Achseneigenschaften in einem Diagramm mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Definieren von XYAxis-Eigenschaften mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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
	// Ändern Sie die X-Achse so, dass sie die Kategorie statt des Datums anzeigt, sodass alle Punkte in gleichen Abständen auf der X-Achse platziert werden.
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

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET Eigenschaften für die X- und Y-Achsen in einem Diagramm definieren. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Achseneigenschaften an Ihre spezifischen Anforderungen anpassen. Aspose.Words für .NET bietet eine umfassende API für die Textverarbeitung mit Diagrammen in Word-Dokumenten, sodass Sie verschiedene Aspekte des Diagramms, einschließlich der Achsen, bearbeiten können.

Durch den Zugriff auf die`ChartAxis` Objekte, die mit dem Diagramm verknüpft sind, können Sie Eigenschaften wie Kategorietyp, Achsenkreuze, Teilstriche, Beschriftungspositionen, Skalierung und mehr ändern. Dank dieser Flexibilität können Sie das Erscheinungsbild und Verhalten der Diagrammachsen anpassen, um Ihre Daten effektiv darzustellen.

Durch die Verwendung von Aspose.Words für .NET können Sie Funktionen zur Diagrammerstellung und -anpassung nahtlos in Ihre .NET-Anwendungen integrieren und die Erstellung professionell aussehender Dokumente mit umfangreichen Visualisierungen automatisieren.

### FAQs

#### F1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Dokumentverarbeitungsbibliothek, mit der Entwickler Word-Dokumente programmgesteuert in .NET-Anwendungen erstellen, bearbeiten und speichern können. Es bietet eine breite Palette von Funktionen für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen.

#### F2. Wie kann ich Aspose.Words für .NET installieren?
Sie können Aspose.Words für .NET installieren, indem Sie es mithilfe des NuGet-Paketmanagers in Visual Studio herunterladen. Suchen Sie einfach im NuGet-Paketmanager nach „Aspose.Words“ und installieren Sie es in Ihrem Projekt.

#### F3. Kann ich mit Aspose.Words für .NET andere Aspekte des Diagramms anpassen?
Ja, Aspose.Words für .NET bietet umfangreiche Möglichkeiten zum Anpassen verschiedener Aspekte eines Diagramms. Neben der Definition der Achseneigenschaften können Sie Diagrammtyp, Datenreihen, Legende, Titel, Plotbereich, Datenbeschriftungen und viele andere Elemente des Diagramms ändern. Die API bietet eine detaillierte Kontrolle über das Erscheinungsbild und Verhalten des Diagramms.

#### F4. Kann ich mit Aspose.Words für .NET verschiedene Diagrammtypen erstellen?
 Ja, Aspose.Words für .NET unterstützt eine Vielzahl von Diagrammtypen, darunter Flächen-, Balken-, Linien-, Kreis-, Streudiagramme und mehr. Sie können das`ChartType` Aufzählung zum Angeben des gewünschten Diagrammtyps beim Einfügen einer Diagrammform in ein Word-Dokument.

#### F5. Kann ich das Diagramm in verschiedenen Formaten speichern?
Ja, Aspose.Words für .NET ermöglicht es Ihnen, das Dokument mit dem Diagramm in verschiedenen Formaten zu speichern, z. B. DOCX, PDF, HTML und mehr. Sie können das geeignete Format entsprechend Ihren Anforderungen auswählen und das`Save` Methode der`Document` Objekt, um das Dokument zu speichern.

#### F6. Kann ich diese Techniken auf mehrere Diagramme in einem Dokument anwenden?
 Ja, Sie können diese Techniken auf mehrere Diagramme in einem Dokument anwenden, indem Sie die erforderlichen Schritte für jedes Diagramm wiederholen. Sie können separate`Chart` Und`ChartAxis` Objekte für jedes Diagramm und passen Sie deren Eigenschaften entsprechend an. Aspose.Words für .NET bietet vollständige Unterstützung für die Textverarbeitung mit mehreren Diagrammen in einem einzigen Dokument.