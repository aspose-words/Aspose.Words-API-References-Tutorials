---
title: Erstellen und anpassen Sie ein Diagramm mit der Form
linktitle: Erstellen und anpassen Sie ein Diagramm mit der Form
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Diagramm mithilfe einer Form in einem Word-Dokument erstellen und anpassen.
type: docs
weight: 10
url: /de/net/programming-with-charts/create-chart-using-shape/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Diagramm mithilfe einer Form in einem Word-Dokument erstellen.

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
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.CreateChartUsingShape.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Beispielquellcode für „Diagramm mithilfe von Form erstellen“ mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET ein Diagramm mithilfe einer Form in einem Word-Dokument erstellen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie eine Diagrammform einfügen und konfigurieren, ihr Erscheinungsbild anpassen und das Dokument speichern. Aspose.Words für .NET bietet umfassende Funktionen für die Textverarbeitung mit Word-Dokumenten und -Diagrammen, sodass Sie professionell aussehende und optisch ansprechende Diagramme direkt in Ihren .NET-Anwendungen erstellen können.

### FAQs

#### Q1. Kann ich mit Aspose.Words für .NET Diagramme in einem Word-Dokument erstellen?
Ja, mit Aspose.Words für .NET können Sie Diagramme in einem Word-Dokument programmgesteuert erstellen. Aspose.Words bietet APIs und Funktionen zum Einfügen verschiedener Diagrammtypen, zum Anpassen ihres Erscheinungsbilds und zum Bearbeiten von Diagrammdaten.

#### Q2. Welche Diagrammtypen werden von Aspose.Words für .NET unterstützt?
Aspose.Words für .NET unterstützt eine Vielzahl von Diagrammtypen, darunter Liniendiagramme, Balkendiagramme, Kreisdiagramme, Flächendiagramme, Streudiagramme und mehr. Sie können den geeigneten Diagrammtyp basierend auf Ihren Daten- und Visualisierungsanforderungen auswählen.

#### Q3. Kann ich das Erscheinungsbild des erstellten Diagramms anpassen?
Ja, Sie können das Erscheinungsbild des erstellten Diagramms mit Aspose.Words für .NET anpassen. Sie können Eigenschaften wie Diagrammtitel, Legendenposition, Datenbeschriftungen, Achsenbeschriftungen, Farben und andere visuelle Elemente ändern, um Ihren spezifischen Design- und Formatierungsanforderungen gerecht zu werden.
