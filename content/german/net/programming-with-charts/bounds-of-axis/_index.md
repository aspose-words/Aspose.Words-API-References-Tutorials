---
title: Achsengrenzen in einem Diagramm
linktitle: Achsengrenzen in einem Diagramm
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Grenzen einer Achse in einem Diagramm festlegen und so den auf der Achse angezeigten Wertebereich steuern.
type: docs
weight: 10
url: /de/net/programming-with-charts/bounds-of-axis/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET die Grenzen einer Achse in einem Diagramm festlegen. Indem Sie ein Diagramm einfügen, Seriendaten hinzufügen und die Achsenskalierung konfigurieren, können Sie die Mindest- und Höchstwerte für die Achse definieren.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Neues Dokument und DocumentBuilder erstellen
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`DocumentBuilder`Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen und Konfigurieren eines Diagramms
 Fügen Sie ein Diagramm in das Dokument ein, indem Sie das`InsertChart` Methode der`DocumentBuilder` Objekt. Legen Sie den gewünschten Diagrammtyp und die gewünschten Abmessungen fest.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 4: Seriendaten hinzufügen
Löschen Sie alle vorhandenen Reihen im Diagramm und fügen Sie neue Reihendaten hinzu. In diesem Beispiel fügen wir eine Reihe mit den Beschriftungen „Element 1“ bis „Element 5“ und den entsprechenden Werten hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Schritt 5: Grenzen der Achse festlegen
 Konfigurieren Sie die Skalierung der Y-Achse, indem Sie die minimalen und maximalen Werte mit den`Scaling.Minimum` Und`Scaling.Maximum` Eigenschaften der Achse.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Schritt 6: Speichern Sie das Dokument
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.BoundsOfAxis.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Beispielquellcode für Bounds Of Axis mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Das ist es! Sie haben die Grenzen einer Achse in einem Diagramm erfolgreich mit Aspose.Words für .NET festgelegt.

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET die Grenzen einer Achse in einem Diagramm festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm einfügen und konfigurieren, Reihendaten hinzufügen und die Mindest- und Höchstwerte für die Achsenskalierung definieren. Aspose.Words für .NET bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Word-Dokumenten, mit der Sie mühelos dynamische und optisch ansprechende Diagramme erstellen können.


### FAQs

#### F1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit Word-Dokumenten zu arbeiten. Sie bietet eine breite Palette an Features und Funktionen zum Erstellen, Bearbeiten und Speichern von Word-Dokumenten.

#### F2. Wie kann ich Aspose.Words für .NET installieren?
Um Aspose.Words für .NET zu installieren, können Sie den NuGet-Paketmanager in Visual Studio verwenden. Suchen Sie einfach im NuGet-Paketmanager nach „Aspose.Words“ und installieren Sie es in Ihrem Projekt.

#### F3. Kann ich Aspose.Words für .NET mit anderen Programmiersprachen verwenden?
Nein, Aspose.Words für .NET ist speziell für .NET-Anwendungen konzipiert. Es funktioniert mit Programmiersprachen wie C# und VB.NET.

#### F4. Gibt es weitere Voraussetzungen für die Verwendung von Aspose.Words für .NET?
Neben der Installation der Aspose.Words für .NET-Bibliothek sollten Sie über Grundkenntnisse in C#-Programmierung und Textverarbeitung mit Word-Dokumenten verfügen. Kenntnisse des .NET-Frameworks sind ebenfalls hilfreich.
