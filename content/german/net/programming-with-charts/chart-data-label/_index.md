---
title: Anpassen der Diagrammdatenbeschriftung
linktitle: Anpassen der Diagrammdatenbeschriftung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Datenbeschriftungen in einem Diagramm hinzufügen und anpassen, um zusätzliche Informationen zu Datenpunkten bereitzustellen.
type: docs
weight: 10
url: /de/net/programming-with-charts/chart-data-label/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET Datenbeschriftungen in einem Diagramm hinzufügen und anpassen. Datenbeschriftungen bieten zusätzliche Informationen zu den Datenpunkten in einem Diagramm.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Neues Dokument und DocumentBuilder erstellen
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`DocumentBuilder`Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen und Konfigurieren eines Diagramms
 Fügen Sie ein Diagramm in das Dokument ein, indem Sie das`InsertChart` Methode der`DocumentBuilder` Objekt. Legen Sie den gewünschten Diagrammtyp und die gewünschten Abmessungen fest.

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
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.ChartDataLabel.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Beispielquellcode für Chart Data Label mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Wenn Sie Datenbeschriftungen zu den Datenpunkten in einem Kreisdiagramm hinzufügen, werden standardmäßig Führungslinien für Datenbeschriftungen angezeigt, die
	// weit außerhalb des Endes der Datenpunkte positioniert. Führungslinien stellen eine visuelle Verbindung zwischen einer Datenbeschriftung und ihrer
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

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET Datenbeschriftungen in einem Diagramm hinzufügen und anpassen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm einfügen, auf die Datenbeschriftungssammlung zugreifen und die Eigenschaften ändern, um das Erscheinungsbild der Datenbeschriftungen anzupassen. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Word-Dokumenten und -Diagrammen, mit der Sie optisch ansprechende und informative Diagramme mit benutzerdefinierten Datenbeschriftungen erstellen können.

### FAQs

#### F1. Was sind Datenbeschriftungen in einem Diagramm?
Datenbeschriftungen in einem Diagramm liefern zusätzliche Informationen zu den im Diagramm dargestellten Datenpunkten. Je nach Diagrammtyp und -konfiguration können sie Werte, Kategorien, Reihennamen, Prozentsätze oder andere relevante Details anzeigen.

#### F2. Kann ich das Erscheinungsbild von Datenbeschriftungen anpassen?
Ja, Sie können das Erscheinungsbild von Datenbeschriftungen in einem Diagramm anpassen. Aspose.Words für .NET bietet Optionen zum Ändern verschiedener Eigenschaften von Datenbeschriftungen, z. B. zum Anzeigen von Legendenschlüsseln, Führungslinien, Kategorienamen, Seriennamen, Werten und mehr. Sie können auch Trennzeichen festlegen und die Beschriftungen formatieren, um Ihren spezifischen Anforderungen gerecht zu werden.

#### F3. Kann ich jedem Diagrammtyp Datenbeschriftungen hinzufügen?
Ja, Sie können Datenbeschriftungen zu verschiedenen Diagrammtypen hinzufügen, darunter Balkendiagramme, Kreisdiagramme, Liniendiagramme und mehr. Der Vorgang zum Hinzufügen und Anpassen von Datenbeschriftungen kann je nach Diagrammtyp und verwendeter Bibliothek oder Tool leicht variieren.
