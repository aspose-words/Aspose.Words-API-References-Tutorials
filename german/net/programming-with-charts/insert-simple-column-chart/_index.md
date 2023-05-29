---
title: Fügen Sie ein einfaches Säulendiagramm ein
linktitle: Fügen Sie ein einfaches Säulendiagramm ein
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein einfaches Säulendiagramm in ein Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-simple-column-chart/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein einfaches Säulendiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

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

 Als nächstes verwenden Sie die`InsertChart` Methode der`DocumentBuilder` um ein Säulendiagramm in das Dokument einzufügen. Sie können je nach Ihren Anforderungen verschiedene Diagrammtypen und -größen angeben.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Reihendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir mehrere Serien mit jeweils zwei Kategorien hinzu.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Damit ist die Implementierung des Einfügens eines einfachen Säulendiagramms mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Einfaches Säulendiagramm einfügen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Sie können verschiedene Diagrammtypen und -größen angeben.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Standardmäßig generierte Serien löschen.
	seriesColl.Clear();
	// Erstellen Sie ein Array mit Kategorienamen. In diesem Tutorial haben wir zwei Kategorien.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Bitte beachten Sie, dass Datenarrays nicht leer sein dürfen und die gleiche Größe haben müssen.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```