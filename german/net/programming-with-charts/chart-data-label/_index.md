---
title: Passen Sie die Diagrammdatenbeschriftung an
linktitle: Passen Sie die Diagrammdatenbeschriftung an
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Datenbeschriftungen in einem Diagramm hinzufügen und anpassen, um zusätzliche Informationen zu Datenpunkten bereitzustellen.
type: docs
weight: 10
url: /de/net/programming-with-charts/chart-data-label/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET Datenbeschriftungen in einem Diagramm hinzufügen und anpassen. Datenbeschriftungen bieten zusätzliche Informationen zu den Datenpunkten in einem Diagramm.

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
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.ChartDataLabel.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Beispielquellcode für Chart Data Label mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Wenn Sie den Datenpunkten in einem Kreisdiagramm Datenbeschriftungen hinzufügen, werden standardmäßig Führungslinien für Datenbeschriftungen angezeigt
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

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET Datenbeschriftungen in einem Diagramm hinzufügen und anpassen. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm einfügen, auf die Datenbeschriftungssammlung zugreifen und die Eigenschaften ändern, um das Erscheinungsbild der Datenbeschriftungen anzupassen. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Word-Dokumenten und -Diagrammen, sodass Sie optisch ansprechende und informative Diagramme mit benutzerdefinierten Datenbeschriftungen erstellen können.

### FAQs

#### Q1. Was sind Datenbeschriftungen in einem Diagramm?
Datenbeschriftungen in einem Diagramm bieten zusätzliche Informationen zu den im Diagramm dargestellten Datenpunkten. Sie können je nach Diagrammtyp und -konfiguration Werte, Kategorien, Reihennamen, Prozentsätze oder andere relevante Details anzeigen.

#### Q2. Kann ich das Erscheinungsbild von Datenbeschriftungen anpassen?
Ja, Sie können das Erscheinungsbild von Datenbeschriftungen in einem Diagramm anpassen. Aspose.Words für .NET bietet Optionen zum Ändern verschiedener Eigenschaften von Datenbeschriftungen, z. B. zum Anzeigen von Legendenschlüsseln, Führungslinien, Kategorienamen, Reihennamen, Werten und mehr. Sie können auch Trennzeichen festlegen und die Etiketten entsprechend Ihren spezifischen Anforderungen formatieren.

#### Q3. Kann ich jedem Diagrammtyp Datenbeschriftungen hinzufügen?
Ja, Sie können Datenbeschriftungen zu verschiedenen Diagrammtypen hinzufügen, darunter Balkendiagramme, Kreisdiagramme, Liniendiagramme und mehr. Der Vorgang zum Hinzufügen und Anpassen von Datenbeschriftungen kann je nach Diagrammtyp und verwendeter Bibliothek oder Tool leicht variieren.
