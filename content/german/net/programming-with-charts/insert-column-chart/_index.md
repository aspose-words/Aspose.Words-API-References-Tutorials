---
title: Säulendiagramm in ein Word-Dokument einfügen
linktitle: Säulendiagramm in ein Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Säulendiagramm in ein Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-column-chart/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Säulendiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen, indem Sie es mit dem NuGet-Paketmanager installieren.
- Ein Dokumentverzeichnispfad, in dem das Ausgabedokument gespeichert wird.

## Schritt 2: Erstellen Sie ein neues Dokument und fügen Sie ein Diagramm ein.

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

## Schritt 3: Fügen Sie dem Diagramm Reihendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir zwei Kategorien und ihre entsprechenden Werte hinzu.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Damit ist die Implementierung des Einfügens eines Säulendiagramms mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Säulendiagramm einfügen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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

Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Diagrammen in Word-Dokumenten. Säulendiagramme werden häufig zum Anzeigen und Vergleichen von Daten verschiedener Kategorien oder Gruppen verwendet. Mit Aspose.Words für .NET können Sie ganz einfach Säulendiagramme erstellen, die Ihre Daten effektiv visualisieren und wertvolle Erkenntnisse liefern.

Durch die Verwendung von Aspose.Words für .NET können Sie den Prozess der Dokumentenerstellung mit Säulendiagrammen automatisieren und so Zeit und Aufwand bei der manuellen Dokumentenerstellung sparen. Die Bibliothek bietet eine breite Palette an Diagrammtypen und Anpassungsoptionen, sodass Sie optisch ansprechende und datenreiche Diagramme in Ihren Word-Dokumenten erstellen können.

### FAQs

#### Q1. Was ist ein Säulendiagramm?
Ein Säulendiagramm ist ein Diagrammtyp, der Daten in vertikalen Balken oder Säulen darstellt. Jede Spalte stellt normalerweise eine Kategorie oder Gruppe dar, und die Höhe oder Länge der Spalte gibt den Wert der dieser Kategorie zugeordneten Daten an. Säulendiagramme werden häufig verwendet, um Daten verschiedener Kategorien zu vergleichen oder Änderungen im Zeitverlauf zu verfolgen.

#### Q2. Kann ich dem Säulendiagramm mehrere Reihen hinzufügen?
Ja, Sie können mit Aspose.Words für .NET mehrere Reihen zum Säulendiagramm hinzufügen. Jede Reihe stellt eine Reihe von Datenpunkten mit ihren jeweiligen Kategorien und Werten dar. Durch das Hinzufügen mehrerer Reihen können Sie verschiedene Datensätze innerhalb desselben Diagramms vergleichen und analysieren und so einen umfassenden Überblick über Ihre Daten erhalten.

#### Q3. Kann ich das Erscheinungsbild des Säulendiagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Erscheinungsbilds des Säulendiagramms anpassen. Sie können Eigenschaften wie Reihenfarbe, Achsenbeschriftungen, Spaltenbreite und Diagrammbereichsformatierung ändern. Die Bibliothek bietet einen umfangreichen Satz an APIs, um die visuellen Elemente des Diagramms zu steuern und ein individuelles Erscheinungsbild zu erstellen, das Ihren Anforderungen entspricht.

#### Q4. Kann ich das Dokument mit dem eingefügten Säulendiagramm in verschiedenen Formaten speichern?
 Ja, mit Aspose.Words für .NET können Sie das Dokument mit dem eingefügten Säulendiagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und verwenden`Save` Methode der`Document` Objekt zum Speichern des Dokuments. Das eingefügte Säulendiagramm bleibt im gespeicherten Dokument erhalten.

#### F5. Kann ich die Daten und das Erscheinungsbild des Säulendiagramms nach dem Einfügen ändern?
Ja, nachdem Sie das Säulendiagramm in das Dokument eingefügt haben, können Sie dessen Daten und Aussehen mithilfe der von Aspose.Words für .NET bereitgestellten APIs ändern. Sie können die Reihendaten aktualisieren, die Spaltenfarben ändern, Achseneigenschaften anpassen und Formatierungsoptionen anwenden, um dynamische und interaktive Diagramme in Ihren Word-Dokumenten zu erstellen.