---
title: Markieren Sie die Ausrichtung mehrerer Zeilenbeschriftungen in einem Diagramm
linktitle: Markieren Sie die Ausrichtung mehrerer Zeilenbeschriftungen in einem Diagramm
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET mehrzeilige Markierungsbeschriftungen in einer Diagrammachse ausrichten.
type: docs
weight: 10
url: /de/net/programming-with-charts/tick-multi-line-label-alignment/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Ausrichtung von mehrzeiligen Markierungen in einer Diagrammachse festlegen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, auf die Achse zugreifen und die Ausrichtung der Teilstrichbeschriftung ändern.

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

 Als nächstes verwenden Sie die`InsertChart` Methode der`DocumentBuilder` um ein Streudiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Schritt 3: Ausrichtung der Teilstrichbeschriftung festlegen

 Um die Ausrichtung mehrzeiliger Häkchenbeschriftungen festzulegen, greifen Sie auf zu`AxisX` Eigenschaft des Diagramms und legen Sie fest`TickLabelAlignment` Eigenschaft in die gewünschte Ausrichtung. In diesem Beispiel legen wir die Ausrichtung auf fest`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Damit ist die Implementierung der Einstellung der mehrzeiligen Markierungsausrichtung für Häkchen mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für die Ausrichtung mehrzeiliger Markierungen mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Diese Eigenschaft hat nur Auswirkungen auf mehrzeilige Etiketten.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET die Ausrichtung von mehrzeiligen Markierungsbeschriftungen in einer Diagrammachse festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Streudiagramm einfügen, auf die Diagrammachse zugreifen und die Ausrichtung der Teilstrichbeschriftung ändern.

Aspose.Words für .NET bietet leistungsstarke Funktionen zum Bearbeiten von Diagrammen in Word-Dokumenten. Mehrzeilige Häkchenbeschriftungen sind nützlich, wenn Achsenbeschriftungen langen Text enthalten, der über mehrere Zeilen umbrochen oder aufgeteilt werden muss. Durch Festlegen der Ausrichtung der Teilstrichbeschriftung können Sie die horizontale Ausrichtung mehrzeiliger Beschriftungen innerhalb der Diagrammachse steuern und so eine optimale Darstellung und Lesbarkeit gewährleisten.

Durch Anpassen der Ausrichtung der mehrzeiligen Markierungen für Häkchen können Sie das Erscheinungsbild Ihres Diagramms optimieren, insbesondere wenn Sie mit langen oder komplexen Beschriftungen arbeiten. Durch die Ausrichtung der Beschriftungen rechts, links, zentriert oder im Blocksatz können Sie eine ausgewogene und optisch ansprechende Anordnung der Teilstrichbeschriftungen entlang der Achse erreichen.

Mit Aspose.Words für .NET können Sie einfach auf die Ausrichtungseigenschaft der Teilstrichbeschriftungen einer Diagrammachse zugreifen und diese ändern, sodass Sie die volle Kontrolle über das Erscheinungsbild und das Layout der Teilstrichbeschriftungen in Ihren Word-Dokumentdiagrammen haben.

### FAQs

#### Q1. Was sind mehrzeilige Markierungen in einer Diagrammachse?
Mehrzeilige Häkchenbeschriftungen in einer Diagrammachse beziehen sich auf Achsenbeschriftungen, die sich über mehrere Zeilen erstrecken, wenn der Beschriftungstext lang ist oder einen Umbruch erfordert, damit er in den verfügbaren Platz passt. Anstatt den Beschriftungstext abzuschneiden oder visuelle Unordnung zu verursachen, teilt die Diagrammachse die Beschriftungen automatisch in mehrere Zeilen auf, um die Lesbarkeit zu gewährleisten. Mehrzeilige Beschriftungen mit Häkchen sind besonders nützlich, wenn Sie in Diagrammen mit langen Kategorie- oder Wertebeschriftungen arbeiten.

#### Q2. Kann ich die Ausrichtung von Teilstrichbeschriftungen in einer Diagrammachse anpassen?
 Ja, Sie können die Ausrichtung von Teilstrichbeschriftungen in einer Diagrammachse mit Aspose.Words für .NET anpassen. Durch den Zugriff auf`TickLabelAlignment` Eigentum der`ChartAxis` Objekt können Sie die gewünschte Ausrichtung für die Teilstrichbeschriftungen festlegen. Zu den Ausrichtungsoptionen gehören die Ausrichtung links, rechts, zentriert oder im Blocksatz. Durch Anpassen der Ausrichtung können Sie die horizontale Positionierung der Teilstrichbeschriftungen entlang der Diagrammachse steuern und so eine ordnungsgemäße Lesbarkeit und visuelle Darstellung gewährleisten.

#### Q3. Wann sollte ich in Betracht ziehen, die Ausrichtung der Teilstrichbeschriftung in einer Diagrammachse zu ändern?
Das Ändern der Ausrichtung der Teilstrichbeschriftung in einer Diagrammachse ist von Vorteil, wenn Sie lange oder mehrzeilige Beschriftungen haben, die eine optimale Darstellung und Lesbarkeit erfordern. Durch Anpassen der Ausrichtung können Sie sicherstellen, dass die Beschriftungen richtig ausgerichtet und beabstandet sind und Überlappungen oder Abschneiden vermieden werden. Erwägen Sie eine Änderung der Ausrichtung der Teilstrichbeschriftungen, wenn Sie Diagramme mit langen Kategorienamen oder ausführlichen Wertebeschriftungen bearbeiten oder in anderen Fällen, in denen die Standardausrichtung nicht das gewünschte visuelle Erscheinungsbild liefert.

#### Q4. Wirkt sich die Ausrichtung der Teilstrichbeschriftungen auf einzeilige Beschriftungen in einer Diagrammachse aus?
Nein, die Ausrichtungseigenschaft der Teilstrichbeschriftung wirkt sich nicht auf einzeilige Beschriftungen in einer Diagrammachse aus. Es wurde speziell für mehrzeilige Etiketten entwickelt, die umwickelt oder geteilt werden müssen. Einzeilige Beschriftungen werden basierend auf den Standardausrichtungseinstellungen der Diagrammachse ausgerichtet. Die Ausrichtungseigenschaft der Teilstrichbeschriftung gilt nur für Beschriftungen, die sich über mehrere Zeilen erstrecken, sodass Sie die Ausrichtung jeder Zeile innerhalb der mehrzeiligen Beschriftung steuern können.

#### F5. Kann ich Teilstrichbeschriftungen für die X-Achse und die Y-Achse in einem Diagramm unterschiedlich ausrichten?
 Ja, Sie können mit Aspose.Words für .NET Teilstrichbeschriftungen für die X- und Y-Achse in einem Diagramm unterschiedlich ausrichten. Die Ausrichtungseigenschaft der Teilstrichbeschriftung ist für jede Diagrammachse spezifisch. Durch den Zugriff auf das entsprechende`ChartAxis` Wenn Sie ein Objekt für die X- oder Y-Achse erstellen, können Sie die Ausrichtung der Teilstrichbeschriftung unabhängig voneinander auf unterschiedliche Werte festlegen. Dadurch haben Sie die Flexibilität, die Teilstrichbeschriftungen je nach Ihren spezifischen Anforderungen für jede Achse im Diagramm unterschiedlich auszurichten.