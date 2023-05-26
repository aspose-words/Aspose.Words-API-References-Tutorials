---
title: Standardoptionen für Datenbeschriftungen
linktitle: Standardoptionen für Datenbeschriftungen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Standardoptionen für Datenbeschriftungen in einem Diagramm festlegen.
type: docs
weight: 10
url: /de/net/programming-with-charts/default-options-for-data-labels/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET Standardoptionen für Datenbeschriftungen in einem Diagramm festlegen. Der bereitgestellte Code zeigt, wie Sie mit Aspose.Words ein Diagramm erstellen, Datenreihen hinzufügen und die Datenbeschriftungen anpassen.

## Schritt 1: Richten Sie das Projekt ein

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Anforderungen erfüllt sind:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es von der offiziellen Aspose-Website herunterladen oder den NuGet-Paketmanager verwenden, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem das Ausgabedokument gespeichert wird.

## Schritt 2: Erstellen Sie ein neues Dokument und fügen Sie ein Diagramm ein

 Lassen Sie uns zunächst ein neues erstellen`Document` Objekt und a`DocumentBuilder` um das Dokument zu erstellen.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Als nächstes fügen wir mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Kreisdiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie Datenreihen zum Diagramm hinzu

Fügen wir nun dem Diagramm eine Datenreihe hinzu. In diesem Beispiel fügen wir drei Kategorien und ihre entsprechenden Werte hinzu.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Schritt 4: Datenbeschriftungen anpassen

 Um die Datenbeschriftungen im Diagramm anzupassen, müssen wir auf zugreifen`ChartDataLabelCollection` Objekt, das mit der Serie verknüpft ist.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Wir können dann verschiedene Eigenschaften des ändern`labels` -Objekt, um die gewünschten Optionen für Datenbeschriftungen festzulegen. In diesem Beispiel aktivieren wir die Anzeige des Prozentsatzes und des Werts, deaktivieren Führungslinien und legen ein benutzerdefiniertes Trennzeichen fest.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Schritt 5: Speichern Sie das Dokument

 Abschließend speichern wir das Dokument mithilfe von im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Damit ist die Implementierung der Festlegung von Standardoptionen für Datenbeschriftungen in einem Diagramm mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Standardoptionen für Datenbeschriftungen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```