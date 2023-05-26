---
title: Intervalleinheit zwischen Beschriftungen auf der Achse
linktitle: Intervalleinheit zwischen Beschriftungen auf der Achse
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Intervalleinheit zwischen Beschriftungen auf der Achse eines Diagramms festlegen.
type: docs
weight: 10
url: /de/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Intervalleinheit zwischen Beschriftungen auf der Achse eines Diagramms festlegen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Achsenbeschriftungen anpassen.

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

 Als nächstes verwenden Sie die`InsertChart` Methode der`DocumentBuilder` um ein Säulendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Seriendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir fünf Elemente mit ihren entsprechenden Werten hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Schritt 4: Passen Sie die Achsenbeschriftungen an

 Um die Intervalleinheit zwischen Beschriftungen auf der X-Achse festzulegen, greifen Sie auf zu`AxisX` Eigenschaft des Diagramms und legen Sie fest`TickLabelSpacing` Eigenschaft auf den gewünschten Wert. In diesem Beispiel legen wir den Abstand auf 2 fest.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Damit ist die Implementierung der Festlegung der Intervalleinheit zwischen Beschriftungen auf der Achse mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für die Intervalleinheit zwischen Beschriftungen auf der Achse mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```