---
title: Erstellen Sie ein Diagramm mithilfe einer Form
linktitle: Erstellen Sie ein Diagramm mithilfe einer Form
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Diagramm mithilfe einer Form in einem Word-Dokument erstellen und anpassen.
type: docs
weight: 10
url: /de/net/programming-with-charts/create-chart-using-shape/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Diagramm mithilfe einer Form in einem Word-Dokument erstellen.

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
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 4: Passen Sie das Diagramm an
Passen Sie das Diagramm an, indem Sie verschiedene Eigenschaften wie den Diagrammtitel und die Legende ändern.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Schritt 5: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.CreateChartUsingShape.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Beispielquellcode für „Diagramm mithilfe von Form erstellen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Bitte beachten Sie, dass der automatisch generierte Titel angezeigt wird, wenn als Titeltext ein Null- oder leerer Wert angegeben wird.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Diagramm mithilfe einer Form in einem Word-Dokument erstellt.