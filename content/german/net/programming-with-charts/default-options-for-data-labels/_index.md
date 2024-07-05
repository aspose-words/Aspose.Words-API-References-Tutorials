---
title: Festlegen von Standardoptionen für Datenbeschriftungen in einem Diagramm
linktitle: Festlegen von Standardoptionen für Datenbeschriftungen in einem Diagramm
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Standardoptionen für Datenbeschriftungen in einem Diagramm festlegen.
type: docs
weight: 10
url: /de/net/programming-with-charts/default-options-for-data-labels/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET Standardoptionen für Datenbeschriftungen in einem Diagramm festlegen. Der bereitgestellte Code zeigt, wie Sie mit Aspose.Words ein Diagramm erstellen, Datenreihen hinzufügen und die Datenbeschriftungen anpassen.

## Schritt 1: Einrichten des Projekts

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Words für .NET-Bibliothek installiert. Sie können sie mit dem NuGet-Paketmanager herunterladen und installieren.
- Ein Dokumentverzeichnispfad, in dem das Ausgabedokument gespeichert wird.

## Schritt 2: Neues Dokument erstellen und Diagramm einfügen

 Erstellen wir zunächst ein neues`Document` Objekt und ein`DocumentBuilder` um das Dokument zu erstellen.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Als nächstes fügen wir ein Diagramm in das Dokument ein, mit dem`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Kreisdiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Datenreihen zum Diagramm hinzufügen

Fügen wir nun dem Diagramm eine Datenreihe hinzu. In diesem Beispiel fügen wir drei Kategorien und die entsprechenden Werte hinzu.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Schritt 4: Datenbeschriftungen anpassen

 Um die Datenbeschriftungen im Diagramm anzupassen, müssen wir auf die`ChartDataLabelCollection` Objekt, das der Serie zugeordnet ist.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Wir können dann verschiedene Eigenschaften des`labels`Objekt, um die gewünschten Optionen für Datenbeschriftungen festzulegen. In diesem Beispiel aktivieren wir die Anzeige von Prozentsatz und Wert, deaktivieren Führungslinien und legen ein benutzerdefiniertes Trennzeichen fest.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Schritt 5: Speichern Sie das Dokument

 Zum Schluss speichern wir das Dokument im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Damit ist die Implementierung zum Festlegen von Standardoptionen für Datenbeschriftungen in einem Diagramm mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Standardoptionen für Datenbeschriftungen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET Standardoptionen für Datenbeschriftungen in einem Diagramm festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm erstellen, Datenreihen hinzufügen und die Datenbeschriftungen an Ihre spezifischen Anforderungen anpassen. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Diagrammen in Word-Dokumenten, mit der Sie verschiedene Diagrammelemente bearbeiten und das gewünschte Erscheinungsbild und die gewünschte Funktionalität erzielen können.

 Durch Festlegen der Eigenschaften des`ChartDataLabelCollection`Objekt, das mit der Diagrammreihe verknüpft ist, können Sie die Anzeige von Datenbeschriftungen steuern, einschließlich Optionen wie die Anzeige von Prozentsätzen, Werten, Führungslinien und benutzerdefinierten Trennzeichen. Diese Flexibilität ermöglicht Ihnen eine effektive Präsentation von Daten und eine Verbesserung der visuellen Darstellung Ihrer Diagramme.

### FAQs

#### F1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert mit .NET-Anwendungen zu erstellen, zu bearbeiten und zu speichern. Sie bietet eine breite Palette von Funktionen für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen.

#### F2. Wie kann ich Aspose.Words für .NET installieren?
Sie können Aspose.Words für .NET installieren, indem Sie es mithilfe des NuGet-Paketmanagers in Visual Studio herunterladen. Suchen Sie einfach im NuGet-Paketmanager nach „Aspose.Words“ und installieren Sie es in Ihrem Projekt.

#### F3. Kann ich mit Aspose.Words für .NET andere Aspekte des Diagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte eines Diagramms anpassen, z. B. Diagrammtyp, Achsenbeschriftungen, Legende, Plotbereich und mehr. Sie können auf verschiedene Eigenschaften des Diagrammobjekts zugreifen und diese ändern, um das gewünschte Erscheinungsbild und Verhalten zu erzielen.

#### F4. Kann ich das Diagramm in verschiedenen Formaten speichern?
 Ja, Aspose.Words für .NET unterstützt das Speichern des Dokuments mit dem Diagramm in verschiedenen Formaten, darunter DOCX, PDF, HTML und mehr. Sie können das entsprechende Format entsprechend Ihren Anforderungen auswählen und das`Save` Methode der`Document` Objekt, um das Dokument zu speichern.

#### F5. Kann ich diese Techniken auf andere Diagrammtypen anwenden?
Ja, die in diesem Tutorial beschriebenen Techniken können auf andere Diagrammtypen angewendet werden, die von Aspose.Words für .NET unterstützt werden. Der Schlüssel besteht darin, auf die relevanten Objekte und Eigenschaften zuzugreifen, die für den Diagrammtyp spezifisch sind, mit dem Sie Textverarbeitung betreiben.