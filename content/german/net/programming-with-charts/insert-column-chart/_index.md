---
title: Säulendiagramm in ein Word-Dokument einfügen
linktitle: Säulendiagramm in ein Word-Dokument einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Säulendiagramm in ein Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-column-chart/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Säulendiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

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

 Verwenden Sie als nächstes die`InsertChart` Methode der`DocumentBuilder` , um ein Säulendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Seriendaten zum Diagramm hinzufügen

Fügen Sie dem Diagramm Reihendaten hinzu. In diesem Beispiel fügen wir zwei Kategorien und die entsprechenden Werte hinzu.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Damit ist die Implementierung zum Einfügen eines Säulendiagramms mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Einfügen eines Säulendiagramms mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET ein Säulendiagramm in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Säulendiagramm einfügen, Reihendaten hinzufügen und das Dokument mit dem Diagramm speichern.

Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Diagrammen in Word-Dokumenten. Säulendiagramme werden häufig verwendet, um Daten in verschiedenen Kategorien oder Gruppen anzuzeigen und zu vergleichen. Mit Aspose.Words für .NET können Sie ganz einfach Säulendiagramme erstellen, die Ihre Daten effektiv visualisieren und wertvolle Erkenntnisse liefern.

Durch die Verwendung von Aspose.Words für .NET können Sie den Prozess der Dokumentenerstellung mit Säulendiagrammen automatisieren und so Zeit und Aufwand bei der manuellen Dokumenterstellung sparen. Die Bibliothek bietet eine breite Palette an Diagrammtypen und Anpassungsoptionen, mit denen Sie optisch ansprechende und datenreiche Diagramme in Ihren Word-Dokumenten erstellen können.

### FAQs

#### F1. Was ist ein Säulendiagramm?
Ein Säulendiagramm ist ein Diagrammtyp, der Daten in vertikalen Balken oder Säulen darstellt. Jede Säule stellt normalerweise eine Kategorie oder Gruppe dar, und die Höhe oder Länge der Säule gibt den Wert der mit dieser Kategorie verknüpften Daten an. Säulendiagramme werden häufig verwendet, um Daten verschiedener Kategorien zu vergleichen oder Änderungen im Zeitverlauf zu verfolgen.

#### F2. Kann ich dem Säulendiagramm mehrere Reihen hinzufügen?
Ja, Sie können mit Aspose.Words für .NET mehrere Reihen zum Säulendiagramm hinzufügen. Jede Reihe stellt eine Reihe von Datenpunkten mit ihren jeweiligen Kategorien und Werten dar. Durch das Hinzufügen mehrerer Reihen können Sie verschiedene Datensätze im selben Diagramm vergleichen und analysieren und erhalten so eine umfassende Ansicht Ihrer Daten.

#### F3. Kann ich das Erscheinungsbild des Säulendiagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Erscheinungsbilds des Säulendiagramms anpassen. Sie können Eigenschaften wie Serienfarbe, Achsenbeschriftungen, Spaltenbreite und Diagrammbereichsformatierung ändern. Die Bibliothek bietet eine Vielzahl von APIs, mit denen Sie die visuellen Elemente des Diagramms steuern und ein individuelles Erscheinungsbild erstellen können, das Ihren Anforderungen entspricht.

#### F4. Kann ich das Dokument mit dem eingefügten Säulendiagramm in verschiedenen Formaten speichern?
 Ja, Aspose.Words für .NET ermöglicht es Ihnen, das Dokument mit dem eingefügten Säulendiagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr zu speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und das`Save` Methode der`Document` Objekt, um das Dokument zu speichern. Das eingefügte Säulendiagramm bleibt im gespeicherten Dokument erhalten.

#### F5. Kann ich die Daten und das Erscheinungsbild des Säulendiagramms nach dem Einfügen ändern?
Ja, nachdem Sie das Säulendiagramm in das Dokument eingefügt haben, können Sie seine Daten und sein Erscheinungsbild mithilfe der von Aspose.Words für .NET bereitgestellten APIs ändern. Sie können die Seriendaten aktualisieren, die Spaltenfarben ändern, Achseneigenschaften anpassen und Formatierungsoptionen anwenden, um dynamische und interaktive Diagramme in Ihren Word-Dokumenten zu erstellen.