---
title: Intervalleinheit zwischen Beschriftungen auf der Achse eines Diagramms
linktitle: Intervalleinheit zwischen Beschriftungen auf der Achse eines Diagramms
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Intervalleinheit zwischen Beschriftungen auf der Achse eines Diagramms festlegen.
type: docs
weight: 10
url: /de/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Intervalleinheit zwischen Beschriftungen auf der Achse eines Diagramms festlegen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Achsenbeschriftungen anpassen.

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

 Als nächstes verwenden Sie die`InsertChart` Methode der`DocumentBuilder` um ein Säulendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Reihendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir fünf Elemente mit ihren entsprechenden Werten hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Schritt 4: Passen Sie die Achsenbeschriftungen an

 Um die Intervalleinheit zwischen Beschriftungen auf der X-Achse festzulegen, greifen Sie auf zu`AxisX` Eigenschaft des Diagramms und legen Sie fest`TickLabelSpacing` Eigenschaft auf den gewünschten Wert. In diesem Beispiel legen wir den Abstand auf 2 fest.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Damit ist die Implementierung der Festlegung der Intervalleinheit zwischen Beschriftungen auf der Achse mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für die Intervalleinheit zwischen Beschriftungen auf der Achse mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET die Intervalleinheit zwischen Beschriftungen auf der Achse eines Diagramms festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Säulendiagramm einfügen, Reihendaten hinzufügen und die Achsenbeschriftungen anpassen, um den Abstand zwischen den Beschriftungen zu steuern.

Aspose.Words für .NET bietet leistungsstarke Funktionen zum Bearbeiten von Diagrammen in Word-Dokumenten. Durch Festlegen der Intervalleinheit zwischen den Beschriftungen auf der Achse können Sie die Anzeigedichte der Beschriftungen steuern und die Lesbarkeit Ihrer Diagramme verbessern. Dadurch können Sie die Darstellung der Daten optimieren und das gesamte Benutzererlebnis verbessern.

Mit Aspose.Words für .NET haben Sie die Flexibilität, verschiedene Aspekte des Diagramms anzupassen, einschließlich der Achsenbeschriftungen. Sie können die gewünschte Intervalleinheit festlegen, um sicherzustellen, dass die Beschriftungen den richtigen Abstand haben und eine klare Darstellung der Datenpunkte bieten.

### FAQs

#### Q1. Was sind Achsenbeschriftungen in einem Diagramm?
Achsenbeschriftungen in einem Diagramm beziehen sich auf die Textdarstellung von Werten entlang der horizontalen (X-Achse) oder vertikalen (Y-Achse) Achse des Diagramms. Mithilfe dieser Beschriftungen können Sie die im Diagramm dargestellten Datenpunkte identifizieren und interpretieren. Achsenbeschriftungen bieten Kontext und ermöglichen es Benutzern, den Maßstab und den Wertebereich im Diagramm zu verstehen.

#### Q2. Wie kann ich den Abstand zwischen Achsenbeschriftungen anpassen?
 Um den Abstand zwischen Achsenbeschriftungen in einem Diagramm mithilfe von Aspose.Words für .NET anzupassen, können Sie auf Folgendes zugreifen`AxisX` oder`AxisY` Eigenschaft des Diagramms und ändern Sie die`TickLabelSpacing` Eigentum. Durch Einstellen der`TickLabelSpacing` B. auf einen bestimmten Wert, können Sie die Intervalleinheit zwischen den Beschriftungen auf der jeweiligen Achse steuern und den Abstand entsprechend Ihren Anforderungen anpassen.

#### Q3. Kann ich unterschiedliche Abstände für die Beschriftungen der X- und Y-Achse festlegen?
Ja, Sie können mit Aspose.Words für .NET unterschiedliche Abstände für die Beschriftungen der X- und Y-Achse festlegen. Greifen Sie auf die entsprechende Achse zu (`AxisX` für X-Achse bzw`AxisY` für die Y-Achse) des Diagramms und ändern Sie die`TickLabelSpacing`Eigenschaft einzeln für jede Achse festlegen. Dadurch können Sie unterschiedliche Intervalleinheiten und Abstände für die Beschriftungen auf der X- und Y-Achse festlegen und so das Erscheinungsbild des Diagramms genau steuern.

#### Q4. Welche Bedeutung hat die Intervalleinheit zwischen Beschriftungen auf der Achse?
Die Intervalleinheit zwischen Beschriftungen auf der Achse bestimmt den Abstand zwischen aufeinanderfolgenden Beschriftungen, die im Diagramm angezeigt werden. Durch Festlegen der Intervalleinheit können Sie die Dichte der Etiketten steuern und sicherstellen, dass sie einen angemessenen Abstand haben, um Überfüllung und Überlappung zu vermeiden. Durch Anpassen der Intervalleinheit können Sie die Daten besser lesbar und optisch ansprechender darstellen.

#### F5. Kann ich andere Eigenschaften der Achsenbeschriftungen ändern?
Ja, Aspose.Words für .NET bietet eine breite Palette von Eigenschaften, um das Erscheinungsbild und Verhalten von Achsenbeschriftungen anzupassen. Sie können Eigenschaften wie Schriftart, Größe, Farbe, Ausrichtung, Ausrichtung und mehr ändern, um die gewünschte Formatierung und den gewünschten Stil für die Achsenbeschriftungen zu erreichen. Die Bibliothek bietet umfassende Kontrolle über Diagrammelemente und ermöglicht Ihnen die Erstellung professionell aussehender Diagramme, die auf Ihre spezifischen Anforderungen zugeschnitten sind.