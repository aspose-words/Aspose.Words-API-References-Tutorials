---
title: Anpassen eines einzelnen Diagrammdatenpunkts in einem Diagramm
linktitle: Anpassen eines einzelnen Diagrammdatenpunkts in einem Diagramm
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET einen einzelnen Datenpunkt in einem Diagramm anpassen.
type: docs
weight: 10
url: /de/net/programming-with-charts/single-chart-data-point/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET einen einzelnen Datenpunkt in einem Diagramm anpassen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, auf bestimmte Datenpunkte zugreifen und deren Eigenschaften ändern.

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

 Verwenden Sie als nächstes die`InsertChart` Methode der`DocumentBuilder` , um ein Liniendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Auf Datenpunkte zugreifen und diese anpassen

 Um einzelne Datenpunkte zu ändern, müssen Sie auf die`ChartDataPointCollection` der Reihe und wählen Sie über den Index den gewünschten Datenpunkt aus.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Damit ist die Implementierung der Anpassung eines einzelnen Datenpunkts in einem Diagramm mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für einen einzelnen Diagrammdatenpunkt mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET einen einzelnen Datenpunkt in einem Diagramm anpassen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Liniendiagramm einfügen, auf bestimmte Datenpunkte innerhalb der Diagrammreihe zugreifen und deren Eigenschaften ändern, um die gewünschte Anpassung zu erreichen.

Aspose.Words für .NET bietet leistungsstarke Funktionen zum Bearbeiten von Diagrammen in Word-Dokumenten. Durch den Zugriff auf einzelne Datenpunkte innerhalb einer Diagrammreihe können Sie bestimmte Änderungen vornehmen, um deren Erscheinungsbild und Verhalten anzupassen. Auf diese Weise können Sie bestimmte Datenpunkte hervorheben, Markierungssymbole ändern, Markierungsgrößen anpassen und vieles mehr, um die visuelle Darstellung Ihres Diagramms zu verbessern.

Durch das Anpassen einzelner Datenpunkte haben Sie die Flexibilität, wichtige Daten hervorzuheben oder bestimmte Trends in Ihrem Diagramm hervorzuheben. Mit Aspose.Words für .NET können Sie problemlos auf Datenpunkte in verschiedenen Diagrammtypen zugreifen und diese ändern, sodass Sie optisch ansprechende und informative Diagramme in Ihren Word-Dokumenten erstellen können.

### FAQs

#### F1. Kann ich mehrere Datenpunkte in einem Diagramm anpassen?
 Ja, Sie können mehrere Datenpunkte in einem Diagramm mit Aspose.Words für .NET anpassen. Durch Zugriff auf die`ChartDataPointCollection`einer Reihe können Sie mehrere Datenpunkte basierend auf ihren Indizes auswählen und ändern. Verwenden Sie eine Schleife oder einzelne Zuweisungen, um die gewünschten Eigenschaften für jeden Datenpunkt zu ändern. Auf diese Weise können Sie verschiedene Anpassungen auf mehrere Datenpunkte innerhalb desselben Diagramms anwenden.

#### F2. Wie kann ich das Markierungssymbol für einen Datenpunkt ändern?
 Um das Markierungssymbol für einen Datenpunkt in einem Diagramm mit Aspose.Words für .NET zu ändern, müssen Sie auf die`Marker` Eigentum der`ChartDataPoint` Objekt und setzen Sie den`Symbol` -Eigenschaft auf das gewünschte Markierungssymbol. Markierungssymbole stellen die Form oder das Symbol dar, das zur Darstellung jedes Datenpunkts im Diagramm verwendet wird. Sie können aus einer Vielzahl integrierter Markierungssymbole wie Kreis, Quadrat, Raute, Dreieck, Stern und mehr wählen.

#### F3. Kann ich die Größe einer Datenpunktmarkierung anpassen?
 Ja, Sie können die Größe eines Datenpunktmarkers in einem Diagramm mit Aspose.Words für .NET anpassen. Zugriff auf die`Marker` Eigentum der`ChartDataPoint` Objekt und setzen Sie den`Size`-Eigenschaft auf die gewünschte Markierungsgröße. Die Größe der Markierung wird normalerweise in Punkten angegeben, wobei ein größerer Wert eine größere Markierungsgröße darstellt. Durch Anpassen der Markierungsgröße können Sie bestimmte Datenpunkte hervorheben oder sie anhand ihrer Bedeutung unterscheiden.

#### F4. Welche anderen Eigenschaften kann ich für einen Datenpunkt ändern?
Aspose.Words für .NET bietet eine Reihe von Eigenschaften, die Sie für einen Datenpunkt in einem Diagramm ändern können. Zu den häufig geänderten Eigenschaften gehören das Markierungssymbol, die Markierungsgröße, die Markierungsfarbe, die Sichtbarkeit der Datenbeschriftung, die Explosion, die Umkehrung bei negativen Werten und mehr. Mit diesen Eigenschaften können Sie das Erscheinungsbild, das Verhalten und die Interaktivität einzelner Datenpunkte anpassen und so Diagramme erstellen, die auf Ihre spezifischen Anforderungen zugeschnitten sind.

#### F5. Kann ich Datenpunkte in anderen Diagrammtypen anpassen?
Ja, Sie können Datenpunkte in verschiedenen Diagrammtypen mit Aspose.Words für .NET anpassen. Während dieses Tutorial das Anpassen von Datenpunkten in einem Liniendiagramm demonstriert, können Sie ähnliche Techniken auf andere Diagrammtypen wie Säulendiagramme, Balkendiagramme, Kreisdiagramme und mehr anwenden. Der Vorgang umfasst den Zugriff auf die Reihen und Datenpunkte im Diagramm und die entsprechende Änderung ihrer Eigenschaften.