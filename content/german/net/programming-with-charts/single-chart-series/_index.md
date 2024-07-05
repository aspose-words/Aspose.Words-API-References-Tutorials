---
title: Anpassen einzelner Diagrammreihen in einem Diagramm
linktitle: Anpassen einzelner Diagrammreihen in einem Diagramm
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie einzelne Diagrammreihen in einem Diagramm mit Aspose.Words für .NET anpassen.
type: docs
weight: 10
url: /de/net/programming-with-charts/single-chart-series/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET einzelne Diagrammreihen in einem Diagramm anpassen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, auf bestimmte Reihen zugreifen und deren Eigenschaften ändern.

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

## Schritt 3: Auf Diagrammreihen zugreifen und diese anpassen

 Um einzelne Diagrammserien zu ändern, benötigen Sie den Zugriff auf`ChartSeries` Objekte des Diagramms.

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

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Damit ist die Implementierung der Anpassung einer einzelnen Diagrammreihe mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für einzelne Diagrammreihen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Sie können außerdem angeben, ob die Linie, die die Punkte im Diagramm verbindet, mithilfe von Catmull-Rom-Splines geglättet werden soll.
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

Aspose.Words für .NET bietet leistungsstarke Funktionen zum Bearbeiten von Diagrammen in Word-Dokumenten. Durch Zugriff auf einzelne Diagrammreihen können Sie spezifische Änderungen vornehmen, um deren Erscheinungsbild und Verhalten anzupassen. Auf diese Weise können Sie den Reihennamen ändern, die Glättung der Diagrammlinie aktivieren, Markierungen für Datenpunkte anpassen, Farben für negative Werte invertieren und vieles mehr, um die visuelle Darstellung Ihres Diagramms zu verbessern.

Durch das Anpassen einer einzelnen Diagrammreihe haben Sie die Flexibilität, bestimmte Daten hervorzuheben oder bestimmte Trends in Ihrem Diagramm hervorzuheben. Mit Aspose.Words für .NET können Sie problemlos auf die Eigenschaften von Diagrammreihen zugreifen und diese ändern, sodass Sie optisch ansprechende und informative Diagramme in Ihren Word-Dokumenten erstellen können.

### FAQs

#### F1. Kann ich mehrere Diagrammreihen in einem Diagramm anpassen?
 Ja, Sie können mehrere Diagrammreihen in einem Diagramm mit Aspose.Words für .NET anpassen. Durch Zugriff auf die`ChartSeries`Objekte im Diagramm können Sie mehrere Reihen basierend auf ihren Indizes oder bestimmten Kriterien auswählen und ändern. Verwenden Sie eine Schleife oder einzelne Zuweisungen, um die gewünschten Eigenschaften für jede Diagrammreihe zu ändern. Auf diese Weise können Sie verschiedene Anpassungen auf mehrere Reihen innerhalb desselben Diagramms anwenden.

#### F2. Wie kann ich den Namen einer Diagrammreihe ändern?
 Um den Namen einer Diagrammserie in einem Diagramm mit Aspose.Words für .NET zu ändern, müssen Sie auf die`Name` Eigentum der`ChartSeries` Objekt und geben Sie ihm den gewünschten Namen. Der Reihenname wird normalerweise in der Diagrammlegende oder in den Datenbeschriftungen angezeigt und bietet eine beschreibende Bezeichnung für die Reihe. Durch Ändern des Reihennamens können Sie aussagekräftige Namen angeben, die die von jeder Reihe dargestellten Daten widerspiegeln.

#### F3. Was ist die Glättung von Diagrammreihen?
Die Glättung von Diagrammreihen ist eine visuelle Verbesserungstechnik, mit der Sie eine glatte Linie erstellen können, die die Punkte im Diagramm verbindet. Dabei wird ein Glättungsalgorithmus wie Catmull-Rom-Splines angewendet, um zwischen Datenpunkten zu interpolieren und eine optisch ansprechende Kurve zu erstellen. Um die Glättung von Reihen in einem Diagramm mit Aspose.Words für .NET zu aktivieren, rufen Sie die`Smooth` Eigentum der`ChartSeries` Objekt und setzen Sie es auf`true`. Die Glättung kann nützlich sein, um Trends oder Muster in Daten mit unregelmäßigen Schwankungen anzuzeigen.

#### F4. Wie kann ich Markierungen für Datenpunkte in einer Diagrammreihe anpassen?
 Um Markierungen für Datenpunkte in einer Diagrammreihe mit Aspose.Words für .NET anzupassen, benötigen Sie Zugriff auf die`Marker` Eigentum der`ChartSeries` Objekt und ändern Sie dessen Eigenschaften wie`Symbol` Und`Size`. Markierungen sind visuelle Indikatoren, die im Diagramm platziert werden, um einzelne Datenpunkte darzustellen. Sie können aus einer Vielzahl integrierter Markierungssymbole wählen und deren Größe anpassen, um bestimmte Datenpunkte innerhalb der Reihe hervorzuheben oder zu unterscheiden.

#### F5. Kann ich die Farben für negative Werte in einer Diagrammreihe umkehren?
 Ja, Sie können Farben für negative Werte in einer Diagrammreihe mit Aspose.Words für .NET invertieren. Durch Festlegen der`InvertIfNegative` Eigentum der`ChartSeries` Einwände erheben gegen`true`werden die Farben für Datenpunkte mit negativen Werten invertiert, sodass sie sich optisch von positiven Werten unterscheiden. Diese Funktion kann beim Vergleich positiver und negativer Werte in einer Diagrammreihe nützlich sein, da sie eine klare Unterscheidung zwischen den beiden ermöglicht.