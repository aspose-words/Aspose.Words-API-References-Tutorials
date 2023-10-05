---
title: Fügen Sie ein einfaches Säulendiagramm in ein Word-Dokument ein
linktitle: Fügen Sie ein einfaches Säulendiagramm in ein Word-Dokument ein
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein einfaches Säulendiagramm in ein Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-simple-column-chart/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein einfaches Säulendiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen, indem Sie es mit dem NuGet-Paketmanager installieren.
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

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET ein einfaches Säulendiagramm in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Säulendiagramm einfügen, mehrere Reihen mit Kategorien und entsprechenden Werten hinzufügen und das Dokument mit dem Diagramm speichern.

Aspose.Words für .NET bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Diagrammen in Word-Dokumenten. Das einfache Säulendiagramm ist eine effektive Möglichkeit, Daten in verschiedenen Kategorien darzustellen und zu vergleichen. Mit Aspose.Words für .NET können Sie ganz einfach Säulendiagramme mit benutzerdefinierten Daten erstellen, mehrere Reihen für den visuellen Vergleich hinzufügen und das Erscheinungsbild des Diagramms entsprechend Ihren Anforderungen anpassen.

Durch die Verwendung von Aspose.Words für .NET können Sie den Prozess der Dokumentenerstellung mit Säulendiagrammen automatisieren und so Zeit und Aufwand bei der manuellen Dokumentenerstellung sparen. Die Bibliothek bietet eine breite Palette an Diagrammtypen, einschließlich einfacher Säulendiagramme, und bietet verschiedene Anpassungsoptionen, um das Erscheinungsbild des Diagramms an Ihre Bedürfnisse anzupassen.

### FAQs

#### Q1. Was ist ein Säulendiagramm?
Ein Säulendiagramm ist eine Art Diagramm, das Daten mithilfe vertikaler Balken unterschiedlicher Höhe anzeigt. Jede Spalte stellt eine Kategorie dar und die Höhe der Spalte entspricht dem Wert dieser Kategorie. Säulendiagramme werden häufig verwendet, um Daten verschiedener Kategorien zu vergleichen oder Änderungen im Zeitverlauf zu verfolgen.

#### Q2. Kann ich dem Säulendiagramm mehrere Reihen hinzufügen?
Ja, mit Aspose.Words für .NET können Sie dem Säulendiagramm mehrere Reihen hinzufügen. Jede Reihe stellt eine Reihe von Datenpunkten mit ihren jeweiligen Kategorien und Werten dar. Durch das Hinzufügen mehrerer Reihen können Sie verschiedene Datensätze innerhalb desselben Säulendiagramms vergleichen und analysieren und so einen umfassenden Überblick über Ihre Daten erhalten.

#### Q3. Kann ich das Erscheinungsbild des Säulendiagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Erscheinungsbilds des Säulendiagramms anpassen. Sie können Eigenschaften wie Reihenfarbe, Achsenbeschriftungen, Datenbeschriftungen und Diagrammbereichsformatierung ändern. Die Bibliothek bietet einen umfangreichen Satz an APIs, um die visuellen Elemente des Diagramms zu steuern und ein individuelles Erscheinungsbild zu erstellen, das Ihren Anforderungen entspricht.

#### Q4. Kann ich das Dokument mit dem eingefügten Säulendiagramm in verschiedenen Formaten speichern?
 Ja, mit Aspose.Words für .NET können Sie das Dokument mit dem eingefügten Säulendiagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und verwenden`Save` Methode der`Document` Objekt zum Speichern des Dokuments. Das eingefügte Säulendiagramm bleibt im gespeicherten Dokument erhalten.

#### F5. Kann ich die Daten und das Erscheinungsbild des Säulendiagramms nach dem Einfügen ändern?
Ja, nachdem Sie das Säulendiagramm in das Dokument eingefügt haben, können Sie dessen Daten und Aussehen mithilfe der von Aspose.Words für .NET bereitgestellten APIs ändern. Sie können die Reihendaten mit neuen Kategorien und Werten aktualisieren, die Farben und Formatierungen der Spalten ändern, Achseneigenschaften anpassen und verschiedene Formatierungsoptionen anwenden, um dynamische und optisch ansprechende Diagramme in Ihren Word-Dokumenten zu erstellen.