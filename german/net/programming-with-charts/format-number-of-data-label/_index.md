---
title: Formatieren Sie die Nummer des Datenetiketts
linktitle: Formatieren Sie die Nummer des Datenetiketts
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Anzahl der Datenbeschriftungen in einem Diagramm mit Aspose.Words für .NET formatieren. Passen Sie ganz einfach Zahlenformate für Datenbeschriftungen an.
type: docs
weight: 10
url: /de/net/programming-with-charts/format-number-of-data-label/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Anzahl der Datenbeschriftungen in einem Diagramm formatieren. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und das Zahlenformat von Datenbeschriftungen anpassen.

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

 Fügen Sie als Nächstes mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder`In diesem Beispiel fügen wir ein Liniendiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Schritt 3: Fügen Sie dem Diagramm Seriendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir drei Kategorien und ihre entsprechenden Werte hinzu.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Schritt 4: Passen Sie das Zahlenformat der Datenbeschriftungen an

 Um die Anzahl der Datenbeschriftungen zu formatieren, greifen Sie auf zu`DataLabels` Sammlung, die mit der Serie verbunden ist.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

In diesem Beispiel legen wir für jede Datenbeschriftung unterschiedliche Zahlenformate fest. Die erste Datenbeschriftung ist als Währung formatiert, die zweite als Datum und die dritte als Prozentsatz.

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Damit ist die Implementierung der Formatierung der Anzahl der Datenbeschriftungen in einem Diagramm mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für die Formatierung der Nummer des Datenetiketts mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Standardmäßig generierte Serien löschen.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Oder Sie können den Formatcode so festlegen, dass er mit einer Quellzelle verknüpft wird.
	// In diesem Fall wird NumberFormat auf „Allgemein“ zurückgesetzt und von einer Quellzelle geerbt.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```