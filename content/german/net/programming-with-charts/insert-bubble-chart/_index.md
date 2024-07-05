---
title: Blasendiagramm in Word-Dokument einfügen
linktitle: Blasendiagramm in Word-Dokument einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Blasendiagramm in ein Dokument einfügen. Fügen Sie Seriendaten mit X-, Y- und Blasengrößenwerten hinzu.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-bubble-chart/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Blasendiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

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

 Verwenden Sie als nächstes die`InsertChart` Methode der`DocumentBuilder` , um ein Blasendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Seriendaten zum Diagramm hinzufügen

Fügen Sie dem Diagramm Reihendaten hinzu. In diesem Beispiel fügen wir drei Datenpunkte mit entsprechenden X-, Y- und Blasengrößenwerten hinzu.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Damit ist die Implementierung zum Einfügen eines Blasendiagramms mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Einfügen eines Blasendiagramms mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET ein Blasendiagramm in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Blasendiagramm einfügen, Seriendaten hinzufügen und das Dokument mit dem Diagramm speichern.

Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Diagrammen in Word-Dokumenten. Blasendiagramme eignen sich ideal zur Visualisierung dreidimensionaler Daten, wobei jeder Datenpunkt durch eine Blase mit X- und Y-Koordinaten und einem Größenwert dargestellt wird. Mit Aspose.Words für .NET können Sie dynamische und informative Blasendiagramme erstellen, die die visuelle Darstellung Ihrer Daten verbessern.

Durch die Verwendung von Aspose.Words für .NET können Sie den Prozess der Dokumenterstellung mit Blasendiagrammen automatisieren und so Zeit und Aufwand bei der manuellen Dokumenterstellung sparen. Die Bibliothek bietet eine breite Palette an Diagrammtypen und Anpassungsoptionen, mit denen Sie optisch ansprechende und datenreiche Diagramme in Ihren Word-Dokumenten erstellen können.

### FAQs

#### F1. Was ist ein Blasendiagramm?
Ein Blasendiagramm ist ein Diagrammtyp, der dreidimensionale Daten mithilfe von Blasen oder Kugeln anzeigt. Jeder Datenpunkt wird durch eine Blase dargestellt, wobei die X- und Y-Koordinaten die Position der Blase im Diagramm bestimmen und die Größe der Blase die dritte Dimension der Daten darstellt. Blasendiagramme sind nützlich, um Beziehungen und Muster zwischen mehreren Variablen zu visualisieren.

#### F2. Kann ich dem Blasendiagramm mehrere Reihen hinzufügen?
Ja, Sie können mit Aspose.Words für .NET mehrere Reihen zum Blasendiagramm hinzufügen. Jede Reihe stellt eine Reihe von Datenpunkten mit den jeweiligen X-, Y- und Blasengrößenwerten dar. Durch das Hinzufügen mehrerer Reihen können Sie verschiedene Datensätze im selben Diagramm vergleichen und analysieren und erhalten so eine umfassende Ansicht Ihrer Daten.

#### F3. Kann ich das Erscheinungsbild des Blasendiagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Erscheinungsbilds des Blasendiagramms anpassen. Sie können Eigenschaften wie Serienfarbe, Blasengröße, Achsenbeschriftungen und Diagrammbereichsformatierung ändern. Die Bibliothek bietet eine Vielzahl von APIs, mit denen Sie die visuellen Elemente des Diagramms steuern und ein individuelles Erscheinungsbild erstellen können, das Ihren Anforderungen entspricht.

#### F4. Kann ich das Dokument mit dem eingefügten Blasendiagramm in verschiedenen Formaten speichern?
 Ja, Aspose.Words für .NET ermöglicht es Ihnen, das Dokument mit dem eingefügten Blasendiagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr zu speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und das`Save` Methode der`Document` Objekt, um das Dokument zu speichern. Das eingefügte Blasendiagramm bleibt im gespeicherten Dokument erhalten.

#### F5. Kann ich die Daten und das Erscheinungsbild des Blasendiagramms nach dem Einfügen ändern?
Ja, nachdem Sie das Blasendiagramm in das Dokument eingefügt haben, können Sie seine Daten und sein Erscheinungsbild mithilfe der von Aspose.Words für .NET bereitgestellten APIs ändern. Sie können die Seriendaten aktualisieren, die Blasengröße ändern, Achseneigenschaften anpassen und Formatierungsoptionen anwenden, um dynamische und interaktive Diagramme in Ihren Word-Dokumenten zu erstellen.