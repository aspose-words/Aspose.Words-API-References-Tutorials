---
title: Einfügen eines einfachen Säulendiagramms in ein Word-Dokument
linktitle: Einfügen eines einfachen Säulendiagramms in ein Word-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein einfaches Säulendiagramm in ein Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-simple-column-chart/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein einfaches Säulendiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Words für die .NET-Bibliothek installiert. Sie können sie mit dem NuGet-Paketmanager herunterladen und installieren.
- Ein Dokumentverzeichnispfad, in dem das Ausgabedokument gespeichert wird.

## Schritt 2: Neues Dokument erstellen und Diagramm einfügen

 Erstelle eine neue`Document` Objekt und ein`DocumentBuilder` um das Dokument zu erstellen.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Verwenden Sie als nächstes die`InsertChart` Methode der`DocumentBuilder` , um ein Säulendiagramm in das Dokument einzufügen. Sie können je nach Bedarf verschiedene Diagrammtypen und -größen angeben.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Seriendaten zum Diagramm hinzufügen

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

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Damit ist die Implementierung zum Einfügen eines einfachen Säulendiagramms mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Einfügen eines einfachen Säulendiagramms mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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
	// Bitte beachten Sie, dass Datenarrays nicht leer sein dürfen und Arrays die gleiche Größe haben müssen.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET ein einfaches Säulendiagramm in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Säulendiagramm einfügen, mehrere Reihen mit Kategorien und entsprechenden Werten hinzufügen und das Dokument mit dem Diagramm speichern.

Aspose.Words für .NET bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Diagrammen in Word-Dokumenten. Das einfache Säulendiagramm ist eine effektive Möglichkeit, Daten in verschiedenen Kategorien darzustellen und zu vergleichen. Mit Aspose.Words für .NET können Sie problemlos Säulendiagramme mit benutzerdefinierten Daten erstellen, mehrere Reihen zum visuellen Vergleich hinzufügen und das Erscheinungsbild des Diagramms Ihren Anforderungen entsprechend anpassen.

Durch die Verwendung von Aspose.Words für .NET können Sie den Prozess der Dokumentenerstellung mit Säulendiagrammen automatisieren und so Zeit und Aufwand bei der manuellen Dokumenterstellung sparen. Die Bibliothek bietet eine breite Palette von Diagrammtypen, einschließlich einfacher Säulendiagramme, und bietet verschiedene Anpassungsoptionen, um das Erscheinungsbild des Diagramms an Ihre Bedürfnisse anzupassen.

### FAQs

#### F1. Was ist ein Säulendiagramm?
Ein Säulendiagramm ist ein Diagrammtyp, der Daten mithilfe vertikaler Balken unterschiedlicher Höhe anzeigt. Jede Säule stellt eine Kategorie dar und die Höhe der Säule entspricht dem Wert dieser Kategorie. Säulendiagramme werden häufig verwendet, um Daten verschiedener Kategorien zu vergleichen oder Änderungen im Zeitverlauf zu verfolgen.

#### F2. Kann ich dem Säulendiagramm mehrere Reihen hinzufügen?
Ja, mit Aspose.Words für .NET können Sie dem Säulendiagramm mehrere Reihen hinzufügen. Jede Reihe stellt eine Reihe von Datenpunkten mit ihren jeweiligen Kategorien und Werten dar. Durch das Hinzufügen mehrerer Reihen können Sie verschiedene Datensätze innerhalb desselben Säulendiagramms vergleichen und analysieren und erhalten so eine umfassende Ansicht Ihrer Daten.

#### F3. Kann ich das Erscheinungsbild des Säulendiagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Erscheinungsbilds des Säulendiagramms anpassen. Sie können Eigenschaften wie Serienfarbe, Achsenbeschriftungen, Datenbeschriftungen und Diagrammbereichsformatierung ändern. Die Bibliothek bietet eine Vielzahl von APIs, mit denen Sie die visuellen Elemente des Diagramms steuern und ein individuelles Erscheinungsbild erstellen können, das Ihren Anforderungen entspricht.

#### F4. Kann ich das Dokument mit dem eingefügten Säulendiagramm in verschiedenen Formaten speichern?
 Ja, Aspose.Words für .NET ermöglicht es Ihnen, das Dokument mit dem eingefügten Säulendiagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr zu speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und das`Save` Methode der`Document` Objekt, um das Dokument zu speichern. Das eingefügte Säulendiagramm bleibt im gespeicherten Dokument erhalten.

#### F5. Kann ich die Daten und das Erscheinungsbild des Säulendiagramms nach dem Einfügen ändern?
Ja, nachdem Sie das Säulendiagramm in das Dokument eingefügt haben, können Sie seine Daten und sein Erscheinungsbild mithilfe der von Aspose.Words für .NET bereitgestellten APIs ändern. Sie können die Seriendaten mit neuen Kategorien und Werten aktualisieren, die Farben und Formatierung der Spalten ändern, Achseneigenschaften anpassen und verschiedene Formatierungsoptionen anwenden, um dynamische und optisch ansprechende Diagramme in Ihren Word-Dokumenten zu erstellen.