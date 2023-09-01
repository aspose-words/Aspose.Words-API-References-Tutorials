---
title: Legen Sie Standardoptionen für Datenbeschriftungen in einem Diagramm fest
linktitle: Legen Sie Standardoptionen für Datenbeschriftungen in einem Diagramm fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Standardoptionen für Datenbeschriftungen in einem Diagramm festlegen.
type: docs
weight: 10
url: /de/net/programming-with-charts/default-options-for-data-labels/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET Standardoptionen für Datenbeschriftungen in einem Diagramm festlegen. Der bereitgestellte Code zeigt, wie Sie mit Aspose.Words ein Diagramm erstellen, Datenreihen hinzufügen und die Datenbeschriftungen anpassen.

## Schritt 1: Richten Sie das Projekt ein

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Anforderungen erfüllt sind:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es mit dem NuGet-Paketmanager herunterladen, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem das Ausgabedokument gespeichert wird.

## Schritt 2: Erstellen Sie ein neues Dokument und fügen Sie ein Diagramm ein

 Lassen Sie uns zunächst ein neues erstellen`Document` Objekt und a`DocumentBuilder` um das Dokument zu erstellen.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Als nächstes fügen wir mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Kreisdiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie Datenreihen zum Diagramm hinzu

Fügen wir nun dem Diagramm eine Datenreihe hinzu. In diesem Beispiel fügen wir drei Kategorien und ihre entsprechenden Werte hinzu.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Schritt 4: Datenbeschriftungen anpassen

 Um die Datenbeschriftungen im Diagramm anzupassen, müssen wir auf zugreifen`ChartDataLabelCollection` Objekt, das mit der Serie verknüpft ist.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Wir können dann verschiedene Eigenschaften des ändern`labels`-Objekt, um die gewünschten Optionen für Datenbeschriftungen festzulegen. In diesem Beispiel aktivieren wir die Anzeige des Prozentsatzes und des Werts, deaktivieren Führungslinien und legen ein benutzerdefiniertes Trennzeichen fest.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Schritt 5: Speichern Sie das Dokument

 Abschließend speichern wir das Dokument mithilfe von im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Damit ist die Implementierung der Festlegung von Standardoptionen für Datenbeschriftungen in einem Diagramm mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Standardoptionen für Datenbeschriftungen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET Standardoptionen für Datenbeschriftungen in einem Diagramm festlegen. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm erstellen, Datenreihen hinzufügen und die Datenbeschriftungen an Ihre spezifischen Anforderungen anpassen. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Diagrammen in Word-Dokumenten, mit der Sie verschiedene Diagrammelemente bearbeiten und das gewünschte Erscheinungsbild und die gewünschte Funktionalität erzielen können.

 Durch Festlegen der Eigenschaften des`ChartDataLabelCollection`Mithilfe des mit der Diagrammreihe verknüpften Objekts können Sie die Anzeige von Datenbeschriftungen steuern, einschließlich Optionen wie der Anzeige von Prozentsätzen, Werten, Führungslinien und benutzerdefinierten Trennzeichen. Diese Flexibilität ermöglicht es Ihnen, Daten effektiv zu präsentieren und die visuelle Darstellung Ihrer Diagramme zu verbessern.

### FAQs

#### Q1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, Word-Dokumente mithilfe von .NET-Anwendungen programmgesteuert zu erstellen, zu bearbeiten und zu speichern. Es bietet zahlreiche Funktionen für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen.

#### Q2. Wie kann ich Aspose.Words für .NET installieren?
Sie können Aspose.Words für .NET installieren, indem Sie es mithilfe des NuGet-Paketmanagers in Visual Studio herunterladen. Suchen Sie einfach im NuGet-Paketmanager nach „Aspose.Words“ und installieren Sie es in Ihrem Projekt.

#### Q3. Kann ich andere Aspekte des Diagramms mit Aspose.Words für .NET anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte eines Diagramms anpassen, z. B. Diagrammtyp, Achsenbeschriftungen, Legende, Diagrammbereich und mehr. Sie können auf verschiedene Eigenschaften des Diagrammobjekts zugreifen und diese ändern, um das gewünschte Erscheinungsbild und Verhalten zu erzielen.

#### Q4. Kann ich das Diagramm in verschiedenen Formaten speichern?
 Ja, Aspose.Words für .NET unterstützt das Speichern des Dokuments mit dem Diagramm in verschiedenen Formaten, einschließlich DOCX, PDF, HTML und mehr. Sie können je nach Ihren Anforderungen das passende Format auswählen und nutzen`Save` Methode der`Document` Objekt zum Speichern des Dokuments.

#### F5. Kann ich diese Techniken auf andere Diagrammtypen anwenden?
Ja, die in diesem Tutorial beschriebenen Techniken können auf andere Diagrammtypen angewendet werden, die von Aspose.Words für .NET unterstützt werden. Der Schlüssel besteht darin, auf die relevanten Objekte und Eigenschaften zuzugreifen, die für den Diagrammtyp spezifisch sind, mit dem Sie Wörter verarbeiten.