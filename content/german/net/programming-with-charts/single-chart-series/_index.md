---
title: Passen Sie einzelne Diagrammreihen in einem Diagramm an
linktitle: Passen Sie einzelne Diagrammreihen in einem Diagramm an
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET einzelne Diagrammreihen in einem Diagramm anpassen.
type: docs
weight: 10
url: /de/net/programming-with-charts/single-chart-series/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET einzelne Diagrammreihen in einem Diagramm anpassen. Der bereitgestellte Quellcode zeigt, wie man ein Diagramm erstellt, auf bestimmte Reihen zugreift und deren Eigenschaften ändert.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen, indem Sie es mit dem NuGet-Paketmanager installieren.
- Ein Dokumentverzeichnispfad, in dem das Ausgabedokument gespeichert wird.

## Schritt 2: Erstellen Sie ein neues Dokument und fügen Sie ein Diagramm ein.

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

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET eine einzelne Diagrammreihe in einem Diagramm anpassen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Liniendiagramm einfügen, auf bestimmte Diagrammreihen zugreifen und deren Eigenschaften ändern, um die gewünschte Anpassung zu erreichen.

Aspose.Words für .NET bietet leistungsstarke Funktionen zum Bearbeiten von Diagrammen in Word-Dokumenten. Durch den Zugriff auf einzelne Diagrammreihen können Sie spezifische Änderungen vornehmen, um deren Erscheinungsbild und Verhalten anzupassen. Dadurch können Sie den Seriennamen ändern, die Glättung der Diagrammlinie aktivieren, Markierungen für Datenpunkte anpassen, Farben für negative Werte umkehren und vieles mehr, um die visuelle Darstellung Ihres Diagramms zu verbessern.

Durch das Anpassen einer einzelnen Diagrammreihe haben Sie die Flexibilität, bestimmte Daten hervorzuheben oder bestimmte Trends in Ihrem Diagramm hervorzuheben. Mit Aspose.Words für .NET können Sie problemlos auf die Eigenschaften von Diagrammreihen zugreifen und diese ändern, sodass Sie optisch ansprechende und informative Diagramme in Ihren Word-Dokumenten erstellen können.

### FAQs

#### Q1. Kann ich mehrere Diagrammreihen in einem Diagramm anpassen?
 Ja, Sie können mit Aspose.Words für .NET mehrere Diagrammreihen in einem Diagramm anpassen. Durch den Zugriff auf`ChartSeries`Mithilfe von Objekten im Diagramm können Sie mehrere Reihen basierend auf ihren Indizes oder bestimmten Kriterien auswählen und ändern. Verwenden Sie eine Schleife oder einzelne Zuweisungen, um die gewünschten Eigenschaften für jede Diagrammreihe zu ändern. Auf diese Weise können Sie unterschiedliche Anpassungen auf mehrere Reihen innerhalb desselben Diagramms anwenden.

#### Q2. Wie kann ich den Namen einer Diagrammreihe ändern?
 Um den Namen einer Diagrammreihe in einem Diagramm mit Aspose.Words für .NET zu ändern, müssen Sie auf Folgendes zugreifen`Name` Eigentum der`ChartSeries` Objekt und setzen Sie es auf den gewünschten Namen. Der Reihenname wird normalerweise in der Diagrammlegende oder in den Datenbeschriftungen angezeigt und bietet eine beschreibende Bezeichnung für die Reihe. Durch Ändern des Seriennamens können Sie aussagekräftige Namen angeben, die die von den einzelnen Serien dargestellten Daten widerspiegeln.

#### Q3. Was ist die Glättung von Diagrammreihen?
Das Glätten von Diagrammreihen ist eine visuelle Verbesserungstechnik, mit der Sie eine glatte Linie erstellen können, die die Punkte im Diagramm verbindet. Es wendet einen Glättungsalgorithmus wie Catmull-Rom-Splines an, um zwischen Datenpunkten zu interpolieren und eine optisch ansprechende Kurve zu erstellen. Um die Reihenglättung in einem Diagramm mit Aspose.Words für .NET zu aktivieren, greifen Sie auf zu`Smooth` Eigentum der`ChartSeries` Objekt und setzen Sie es auf`true`. Die Glättung kann nützlich sein, um Trends oder Muster in Daten mit unregelmäßigen Schwankungen anzuzeigen.

#### Q4. Wie kann ich Markierungen für Datenpunkte in einer Diagrammreihe anpassen?
 Um Markierungen für Datenpunkte in einer Diagrammreihe mithilfe von Aspose.Words für .NET anzupassen, müssen Sie auf Folgendes zugreifen`Marker` Eigentum der`ChartSeries` Objekt und ändern Sie seine Eigenschaften, z`Symbol` Und`Size`. Markierungen sind visuelle Indikatoren, die im Diagramm platziert werden, um einzelne Datenpunkte darzustellen. Sie können aus einer Vielzahl integrierter Markierungssymbole auswählen und deren Größe anpassen, um bestimmte Datenpunkte innerhalb der Serie hervorzuheben oder zu unterscheiden.

#### F5. Kann ich Farben für negative Werte in einer Diagrammreihe umkehren?
 Ja, Sie können mit Aspose.Words für .NET Farben für negative Werte in einer Diagrammreihe umkehren. Durch Einstellen der`InvertIfNegative` Eigentum der`ChartSeries` widersprechen`true`, werden die Farben für Datenpunkte mit negativen Werten invertiert, sodass sie sich optisch von positiven Werten unterscheiden. Diese Funktion kann beim Vergleich positiver und negativer Werte in einer Diagrammreihe nützlich sein und eine klare Unterscheidung zwischen beiden ermöglichen.