---
title: Streudiagramm in Word-Dokument einfügen
linktitle: Streudiagramm in Word-Dokument einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Streudiagramm in ein Dokument einfügen. Fügen Sie Seriendaten mit X- und Y-Koordinaten hinzu.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-scatter-chart/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Streudiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

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

 Verwenden Sie als nächstes die`InsertChart` Methode der`DocumentBuilder` , um ein Streudiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Seriendaten zum Diagramm hinzufügen

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir zwei Sätze von X- und Y-Koordinaten hinzu.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Damit ist die Implementierung zum Einfügen eines Streudiagramms mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Einfügen eines Streudiagramms mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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

Aspose.Words für .NET bietet eine umfassende API für die Textverarbeitung mit Diagrammen in Word-Dokumenten. Streudiagramme sind nützlich zum Visualisieren und Analysieren von Daten mit zwei numerischen Variablen. Mit Aspose.Words für .NET können Sie ganz einfach Streudiagramme erstellen, die die Beziehung zwischen X- und Y-Werten darstellen und Muster oder Trends in den Daten identifizieren.

Durch die Verwendung von Aspose.Words für .NET können Sie den Prozess der Dokumenterstellung mit Streudiagrammen automatisieren und so Zeit und Aufwand bei der manuellen Dokumenterstellung sparen. Die Bibliothek bietet eine breite Palette von Diagrammtypen, einschließlich Streudiagrammen, und bietet verschiedene Anpassungsoptionen, um das Erscheinungsbild des Diagramms Ihren Anforderungen entsprechend anzupassen.

### FAQs

#### F1. Was ist ein Streudiagramm?
Ein Streudiagramm ist ein Diagrammtyp, der die Beziehung zwischen zwei numerischen Variablen darstellt. Es besteht aus einer Reihe von Punkten, die in einem Koordinatenraster aufgetragen sind, wobei eine Variable auf der X-Achse und die andere Variable auf der Y-Achse dargestellt wird. Streudiagramme werden verwendet, um Muster, Korrelationen oder Trends zwischen zwei Datenpunktsätzen zu erkennen.

#### F2. Kann ich dem Streudiagramm mehrere Reihen hinzufügen?
Ja, Sie können mit Aspose.Words für .NET mehrere Reihen zum Streudiagramm hinzufügen. Jede Reihe stellt eine Reihe von Datenpunkten mit ihren jeweiligen X- und Y-Koordinaten dar. Durch das Hinzufügen mehrerer Reihen können Sie verschiedene Datensätze innerhalb desselben Streudiagramms vergleichen und analysieren und erhalten so eine umfassende Ansicht Ihrer Daten.

#### F3. Kann ich das Erscheinungsbild des Streudiagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Erscheinungsbilds des Streudiagramms anpassen. Sie können Eigenschaften wie Serienfarbe, Markierungsform, Achsenbeschriftungen und Diagrammbereichsformatierung ändern. Die Bibliothek bietet eine Vielzahl von APIs, mit denen Sie die visuellen Elemente des Diagramms steuern und ein individuelles Erscheinungsbild erstellen können, das Ihren Anforderungen entspricht.

#### F4. Kann ich das Dokument mit dem eingefügten Streudiagramm in verschiedenen Formaten speichern?
Ja, Aspose.Words für .NET ermöglicht es Ihnen, das Dokument mit dem eingefügten Streudiagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr zu speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und das`Save` Methode der`Document` Objekt, um das Dokument zu speichern. Das eingefügte Streudiagramm bleibt im gespeicherten Dokument erhalten.

#### F5. Kann ich die Daten und das Erscheinungsbild des Streudiagramms nach dem Einfügen ändern?
Ja, nachdem Sie das Streudiagramm in das Dokument eingefügt haben, können Sie seine Daten und sein Erscheinungsbild mithilfe der von Aspose.Words für .NET bereitgestellten APIs ändern. Sie können die Seriendaten mit neuen X- und Y-Koordinaten aktualisieren, die Markierungsformen und -farben ändern, Achseneigenschaften anpassen und Formatierungsoptionen anwenden, um dynamische und interaktive Diagramme in Ihren Word-Dokumenten zu erstellen.