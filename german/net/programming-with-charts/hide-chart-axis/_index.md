---
title: Diagrammachse ausblenden
linktitle: Diagrammachse ausblenden
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Diagrammachse in einem Dokument ausblenden. Blenden Sie die Achse aus, um eine übersichtlichere und fokussiertere Diagrammanzeige zu erzielen.
type: docs
weight: 10
url: /de/net/programming-with-charts/hide-chart-axis/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Diagrammachse in einem Dokument ausblenden. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Diagrammachse ausblenden.

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

 Fügen Sie als Nächstes mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Säulendiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Seriendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir fünf Elemente und ihre entsprechenden Werte hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Schritt 4: Diagrammachse ausblenden

 Um die Diagrammachse auszublenden, greifen Sie auf zu`AxisY` Eigenschaft des Diagramms und legen Sie fest`Hidden` Eigentum zu`true`.

```csharp
chart.AxisY.Hidden = true;
```

In diesem Beispiel blenden wir die Y-Achse des Diagramms aus.

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Damit ist die Implementierung des Ausblendens der Diagrammachse mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Diagrammachse ausblenden mit Aspose.Words für .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```