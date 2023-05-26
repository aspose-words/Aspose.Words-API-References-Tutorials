---
title: Diagrammdatenbeschriftung
linktitle: Diagrammdatenbeschriftung
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Datenbeschriftungen in einem Diagramm hinzufügen und anpassen, um zusätzliche Informationen zu Datenpunkten bereitzustellen.
type: docs
weight: 10
url: /de/net/programming-with-charts/chart-data-label/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET Datenbeschriftungen in einem Diagramm hinzufügen und anpassen. Datenbeschriftungen bieten zusätzliche Informationen zu den Datenpunkten in einem Diagramm.

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

## Schritt 3: Einfügen und Konfigurieren eines Diagramms
 Fügen Sie mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder` Objekt. Legen Sie den gewünschten Diagrammtyp und die gewünschten Abmessungen fest.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 4: Datenbeschriftungen anpassen
Greifen Sie auf die Datenbeschriftungssammlung der Diagrammreihe zu und ändern Sie verschiedene Eigenschaften, um das Erscheinungsbild der Datenbeschriftungen anzupassen.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Schritt 5: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.ChartDataLabel.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Beispielquellcode für Chart Data Label mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	//Wenn Sie den Datenpunkten in einem Kreisdiagramm Datenbeschriftungen hinzufügen, werden standardmäßig Führungslinien für Datenbeschriftungen angezeigt
	// weit außerhalb des Endes der Datenpunkte positioniert. Führungslinien stellen eine visuelle Verbindung zwischen einem Datenetikett und seinem Datenetikett her
	// entsprechenden Datenpunkt.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich Datenbeschriftungen in einem Diagramm hinzugefügt und angepasst.