---
title: Grenzen der Achse in einem Diagramm
linktitle: Grenzen der Achse in einem Diagramm
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Grenzen einer Achse in einem Diagramm festlegen und den auf der Achse angezeigten Wertebereich steuern.
type: docs
weight: 10
url: /de/net/programming-with-charts/bounds-of-axis/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Grenzen einer Achse in einem Diagramm festlegen. Durch Einfügen eines Diagramms, Hinzufügen von Reihendaten und Konfigurieren der Achsenskalierung können Sie die Mindest- und Höchstwerte für die Achse definieren.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
 Erstellen Sie eine neue Instanz von`Document` Klasse und a`DocumentBuilder` Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen und Konfigurieren eines Diagramms
 Fügen Sie mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder` Objekt. Legen Sie den gewünschten Diagrammtyp und die gewünschten Abmessungen fest.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 4: Seriendaten hinzufügen
Löschen Sie alle vorhandenen Serien im Diagramm und fügen Sie neue Seriendaten hinzu. In diesem Beispiel fügen wir eine Reihe mit den Bezeichnungen „Artikel 1“ bis „Artikel 5“ und entsprechenden Werten hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Schritt 5: Legen Sie die Grenzen der Achse fest
 Konfigurieren Sie die Skalierung der Y-Achse, indem Sie die Minimal- und Maximalwerte mithilfe von festlegen`Scaling.Minimum` Und`Scaling.Maximum` Eigenschaften der Achse.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Schritt 6: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithCharts.BoundsOfAxis.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Beispielquellcode für Bounds Of Axis mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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

Das ist es! Sie haben die Grenzen einer Achse in einem Diagramm mit Aspose.Words für .NET erfolgreich festgelegt.

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET die Grenzen einer Achse in einem Diagramm festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein Diagramm einfügen und konfigurieren, Reihendaten hinzufügen und die Mindest- und Höchstwerte für die Achsenskalierung definieren. Aspose.Words für .NET bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Word-Dokumenten, mit der Sie problemlos dynamische und optisch ansprechende Diagramme erstellen können.


### FAQs

#### Q1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit Word-Dokumenten zu arbeiten. Es bietet eine breite Palette an Features und Funktionalitäten zum Erstellen, Bearbeiten und Speichern von Word-Dokumenten.

#### Q2. Wie kann ich Aspose.Words für .NET installieren?
Um Aspose.Words für .NET zu installieren, können Sie den NuGet-Paketmanager in Visual Studio verwenden. Suchen Sie einfach im NuGet-Paketmanager nach „Apose.Words“ und installieren Sie es in Ihrem Projekt.

#### Q3. Kann ich Aspose.Words für .NET mit anderen Programmiersprachen verwenden?
Nein, Aspose.Words für .NET wurde speziell für .NET-Anwendungen entwickelt. Es funktioniert mit Programmiersprachen wie C# und VB.NET.

#### Q4. Gibt es weitere Voraussetzungen für die Verwendung von Aspose.Words für .NET?
Neben der Installation der Aspose.Words für .NET-Bibliothek sollten Sie über Grundkenntnisse in C#-Programmierung und Textverarbeitung mit Word-Dokumenten verfügen. Kenntnisse des .NET-Frameworks sind ebenfalls hilfreich.
