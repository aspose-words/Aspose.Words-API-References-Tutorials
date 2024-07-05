---
title: Intervalleinheit zwischen Beschriftungen auf einer Diagrammachse
linktitle: Intervalleinheit zwischen Beschriftungen auf einer Diagrammachse
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Intervalleinheit zwischen Beschriftungen auf der Achse eines Diagramms festlegen.
type: docs
weight: 10
url: /de/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET die Intervalleinheit zwischen Beschriftungen auf den Achsen eines Diagramms festlegen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und die Achsenbeschriftungen anpassen.

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

Fügen Sie dem Diagramm Reihendaten hinzu. In diesem Beispiel fügen wir fünf Elemente mit den entsprechenden Werten hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Schritt 4: Anpassen der Achsenbeschriftungen

 Um die Intervalleinheit zwischen den Beschriftungen auf der X-Achse einzustellen, rufen Sie das`AxisX` des Diagramms und legen Sie die`TickLabelSpacing` -Eigenschaft auf den gewünschten Wert. In diesem Beispiel setzen wir den Abstand auf 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Damit ist die Implementierung der Festlegung der Intervalleinheit zwischen Beschriftungen auf der Achse mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Intervalleinheit zwischen Beschriftungen auf der Achse mit Aspose.Words für .NET 

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
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET die Intervalleinheit zwischen Beschriftungen auf der Achse eines Diagramms festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Säulendiagramm einfügen, Seriendaten hinzufügen und die Achsenbeschriftungen anpassen, um den Abstand zwischen den Beschriftungen zu steuern.

Aspose.Words für .NET bietet leistungsstarke Funktionen zum Bearbeiten von Diagrammen in Word-Dokumenten. Durch Festlegen der Intervalleinheit zwischen den Beschriftungen auf der Achse können Sie die Anzeigedichte der Beschriftungen steuern und die Lesbarkeit Ihrer Diagramme verbessern. Auf diese Weise können Sie die Darstellung der Daten optimieren und das allgemeine Benutzererlebnis verbessern.

Mit Aspose.Words für .NET haben Sie die Flexibilität, verschiedene Aspekte des Diagramms anzupassen, einschließlich der Achsenbeschriftungen. Sie können die gewünschte Intervalleinheit festlegen, um sicherzustellen, dass die Beschriftungen den richtigen Abstand haben und eine klare Darstellung der Datenpunkte bieten.

### FAQs

#### F1. Was sind Achsenbeschriftungen in einem Diagramm?
Achsenbeschriftungen in einem Diagramm beziehen sich auf die Textdarstellung von Werten entlang der horizontalen (X-Achse) oder vertikalen (Y-Achse) Achse des Diagramms. Diese Beschriftungen helfen dabei, die im Diagramm dargestellten Datenpunkte zu identifizieren und zu interpretieren. Achsenbeschriftungen bieten Kontext und ermöglichen Benutzern, die Skala und den Wertebereich im Diagramm zu verstehen.

#### F2. Wie kann ich den Abstand zwischen Achsenbeschriftungen anpassen?
 Um den Abstand zwischen Achsenbeschriftungen in einem Diagramm mit Aspose.Words für .NET anzupassen, können Sie auf die`AxisX` oder`AxisY` des Diagramms und ändern Sie die`TickLabelSpacing` Eigenschaft. Durch das Setzen der`TickLabelSpacing` Auf einen bestimmten Wert können Sie die Intervalleinheit zwischen den Beschriftungen auf der jeweiligen Achse steuern und den Abstand entsprechend Ihren Anforderungen anpassen.

#### F3. Kann ich für die Beschriftungen der X- und Y-Achse unterschiedliche Abstände festlegen?
Ja, Sie können mit Aspose.Words für .NET unterschiedliche Abstände für die Beschriftungen der X- und Y-Achse festlegen. Greifen Sie auf die jeweilige Achse zu (`AxisX` für X-Achse oder`AxisY` für die Y-Achse) des Diagramms und ändern Sie die`TickLabelSpacing`-Eigenschaft für jede Achse einzeln festlegen. Dadurch können Sie unterschiedliche Intervalleinheiten und Abstände für die Beschriftungen auf der X- und Y-Achse festlegen und so das Erscheinungsbild des Diagramms fein granular steuern.

#### F4. Welche Bedeutung hat die Intervalleinheit zwischen den Beschriftungen auf der Achse?
Die Intervalleinheit zwischen den Beschriftungen auf der Achse bestimmt den Abstand zwischen aufeinanderfolgenden Beschriftungen, die im Diagramm angezeigt werden. Durch Festlegen der Intervalleinheit können Sie die Dichte der Beschriftungen steuern und sicherstellen, dass sie angemessen verteilt sind, um Überfüllung und Überlappungen zu vermeiden. Durch Anpassen der Intervalleinheit können Sie die Daten besser lesbar und optisch ansprechender darstellen.

#### F5. Kann ich andere Eigenschaften der Achsenbeschriftungen ändern?
Ja, Aspose.Words für .NET bietet eine breite Palette von Eigenschaften, um das Erscheinungsbild und Verhalten von Achsenbeschriftungen anzupassen. Sie können Eigenschaften wie Schriftart, Größe, Farbe, Ausrichtung, Ausrichtung und mehr ändern, um die gewünschte Formatierung und den gewünschten Stil für die Achsenbeschriftungen zu erreichen. Die Bibliothek bietet umfassende Kontrolle über Diagrammelemente, sodass Sie professionell aussehende Diagramme erstellen können, die auf Ihre spezifischen Anforderungen zugeschnitten sind.