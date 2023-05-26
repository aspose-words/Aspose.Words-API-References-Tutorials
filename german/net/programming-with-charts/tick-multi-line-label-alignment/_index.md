---
title: Aktivieren Sie die Option „Mehrzeilige Beschriftungsausrichtung“.
linktitle: Aktivieren Sie die Option „Mehrzeilige Beschriftungsausrichtung“.
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET mehrzeilige Markierungsbeschriftungen in einer Diagrammachse ausrichten.
type: docs
weight: 10
url: /de/net/programming-with-charts/tick-multi-line-label-alignment/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Ausrichtung von mehrzeiligen Markierungen in einer Diagrammachse festlegen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, auf die Achse zugreifen und die Ausrichtung der Teilstrichbeschriftung ändern.

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

 Als nächstes verwenden Sie die`InsertChart` Methode der`DocumentBuilder` um ein Streudiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Schritt 3: Ausrichtung der Teilstrichbeschriftung festlegen

 Um die Ausrichtung mehrzeiliger Häkchenbeschriftungen festzulegen, greifen Sie auf zu`AxisX` Eigenschaft des Diagramms und legen Sie fest`TickLabelAlignment` Eigenschaft in die gewünschte Ausrichtung. In diesem Beispiel legen wir die Ausrichtung auf fest`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Damit ist die Implementierung der Einstellung der mehrzeiligen Markierungsausrichtung für Häkchen mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für die Ausrichtung mehrzeiliger Markierungen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Diese Eigenschaft hat nur Auswirkungen auf mehrzeilige Etiketten.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```