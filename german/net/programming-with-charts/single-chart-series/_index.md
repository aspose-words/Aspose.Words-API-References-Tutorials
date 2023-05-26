---
title: Einzelne Diagrammserie
linktitle: Einzelne Diagrammserie
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET einzelne Diagrammreihen in einem Diagramm anpassen.
type: docs
weight: 10
url: /de/net/programming-with-charts/single-chart-series/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET einzelne Diagrammreihen in einem Diagramm anpassen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, auf bestimmte Reihen zugreifen und deren Eigenschaften ändern.

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

 Als nächstes verwenden Sie die`InsertChart` Methode der`DocumentBuilder` um ein Liniendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Auf Diagrammreihen zugreifen und diese anpassen

 Um einzelne Diagrammreihen zu ändern, müssen Sie auf zugreifen`ChartSeries` Objekte des Diagramms.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Damit ist die Implementierung der Anpassung einer einzelnen Diagrammreihe mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Single Chart Series mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Sie können auch festlegen, ob die Linie, die die Punkte im Diagramm verbindet, mithilfe von Catmull-Rom-Splines geglättet werden soll.
	series0.Smooth = true;
	series1.Smooth = true;
	// Gibt an, ob das übergeordnete Element standardmäßig seine Farben invertieren soll, wenn der Wert negativ ist.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```