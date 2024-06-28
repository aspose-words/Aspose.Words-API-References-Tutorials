---
title: Fügen Sie ein Streudiagramm in ein Word-Dokument ein
linktitle: Fügen Sie ein Streudiagramm in ein Word-Dokument ein
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Streudiagramm in ein Dokument einfügen. Fügen Sie Seriendaten mit X- und Y-Koordinaten hinzu.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-scatter-chart/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Streudiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

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

 Als nächstes verwenden Sie die`InsertChart` Methode der`DocumentBuilder` um ein Streudiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Reihendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir zwei Sätze von X- und Y-Koordinaten hinzu.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Damit ist die Implementierung des Einfügens eines Streudiagramms mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für das Einfügen eines Streudiagramms mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET ein Streudiagramm in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Streudiagramm einfügen, Reihendaten mit X- und Y-Koordinaten hinzufügen und das Dokument mit dem Diagramm speichern.

Aspose.Words für .NET bietet eine umfassende API für die Textverarbeitung mit Diagrammen in Word-Dokumenten. Streudiagramme eignen sich zur Visualisierung und Analyse von Daten mit zwei numerischen Variablen. Mit Aspose.Words für .NET können Sie ganz einfach Streudiagramme erstellen, die die Beziehung zwischen X- und Y-Werten darstellen und Muster oder Trends in den Daten erkennen.

Durch die Verwendung von Aspose.Words für .NET können Sie den Prozess der Dokumentenerstellung mit Streudiagrammen automatisieren und so Zeit und Aufwand bei der manuellen Dokumentenerstellung sparen. Die Bibliothek bietet eine breite Palette an Diagrammtypen, einschließlich Streudiagrammen, und bietet verschiedene Anpassungsoptionen, um das Erscheinungsbild des Diagramms an Ihre Bedürfnisse anzupassen.

### FAQs

#### Q1. Was ist ein Streudiagramm?
Ein Streudiagramm ist eine Art Diagramm, das die Beziehung zwischen zwei numerischen Variablen anzeigt. Es besteht aus einer Reihe von Punkten, die auf einem Koordinatengitter aufgetragen sind, wobei eine Variable auf der X-Achse und die andere Variable auf der Y-Achse dargestellt wird. Streudiagramme werden verwendet, um Muster, Korrelationen oder Trends zwischen zwei Sätzen von Datenpunkten zu identifizieren.

#### Q2. Kann ich dem Streudiagramm mehrere Reihen hinzufügen?
Ja, Sie können mit Aspose.Words für .NET mehrere Reihen zum Streudiagramm hinzufügen. Jede Reihe stellt einen Satz von Datenpunkten mit ihren jeweiligen X- und Y-Koordinaten dar. Durch das Hinzufügen mehrerer Reihen können Sie verschiedene Datensätze innerhalb desselben Streudiagramms vergleichen und analysieren und so einen umfassenden Überblick über Ihre Daten erhalten.

#### Q3. Kann ich das Erscheinungsbild des Streudiagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Erscheinungsbilds des Streudiagramms anpassen. Sie können Eigenschaften wie Reihenfarbe, Markierungsform, Achsenbeschriftungen und Diagrammbereichsformatierung ändern. Die Bibliothek bietet einen umfangreichen Satz an APIs, um die visuellen Elemente des Diagramms zu steuern und ein individuelles Erscheinungsbild zu erstellen, das Ihren Anforderungen entspricht.

#### Q4. Kann ich das Dokument mit dem eingefügten Streudiagramm in verschiedenen Formaten speichern?
Ja, mit Aspose.Words für .NET können Sie das Dokument mit dem eingefügten Streudiagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und verwenden`Save` Methode der`Document` Objekt zum Speichern des Dokuments. Das eingefügte Streudiagramm bleibt im gespeicherten Dokument erhalten.

#### F5. Kann ich die Daten und das Erscheinungsbild des Streudiagramms nach dem Einfügen ändern?
Ja, nachdem Sie das Streudiagramm in das Dokument eingefügt haben, können Sie dessen Daten und Aussehen mithilfe der von Aspose.Words für .NET bereitgestellten APIs ändern. Sie können die Seriendaten mit neuen X- und Y-Koordinaten aktualisieren, die Markierungsformen und -farben ändern, Achseneigenschaften anpassen und Formatierungsoptionen anwenden, um dynamische und interaktive Diagramme in Ihren Word-Dokumenten zu erstellen.