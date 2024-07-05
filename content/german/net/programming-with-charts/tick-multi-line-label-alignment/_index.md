---
title: Aktivieren Sie die Option „Ausrichtung mehrerer Zeilenbeschriftungen in einem Diagramm“
linktitle: Aktivieren Sie die Option „Ausrichtung mehrerer Zeilenbeschriftungen in einem Diagramm“
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET mehrzeilige Beschriftungen in einer Diagrammachse ausrichten.
type: docs
weight: 10
url: /de/net/programming-with-charts/tick-multi-line-label-alignment/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET die Ausrichtung von mehrzeiligen Teilstrichbeschriftungen in einer Diagrammachse festlegen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, auf die Achse zugreifen und die Ausrichtung der Teilstrichbeschriftung ändern.

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
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Schritt 3: Ausrichtung der Teilstrichbeschriftung festlegen

 Um die Ausrichtung von mehrzeiligen Markierungsbeschriftungen festzulegen, rufen Sie das`AxisX` des Diagramms und legen Sie die`TickLabelAlignment` Eigenschaft auf die gewünschte Ausrichtung. In diesem Beispiel setzen wir die Ausrichtung auf`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Damit ist die Implementierung der Festlegung der Ausrichtung mehrzeiliger Häkchenbeschriftungen mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für die Ausrichtung mehrzeiliger Tick-Beschriftungen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Diese Eigenschaft wirkt sich nur auf mehrzeilige Beschriftungen aus.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie die Ausrichtung von mehrzeiligen Teilstrichbeschriftungen in einer Diagrammachse mit Aspose.Words für .NET festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Streudiagramm einfügen, auf die Diagrammachse zugreifen und die Ausrichtung der Teilstrichbeschriftung ändern.

Aspose.Words für .NET bietet leistungsstarke Funktionen zum Bearbeiten von Diagrammen in Word-Dokumenten. Mehrzeilige Häkchenbeschriftungen sind nützlich, wenn Achsenbeschriftungen langen Text enthalten, der umgebrochen oder auf mehrere Zeilen aufgeteilt werden muss. Durch Festlegen der Ausrichtung der Häkchenbeschriftung können Sie die horizontale Ausrichtung mehrzeiliger Beschriftungen innerhalb der Diagrammachse steuern und so optimale Darstellung und Lesbarkeit gewährleisten.

Durch Anpassen der Ausrichtung mehrzeiliger Beschriftungen können Sie das Erscheinungsbild Ihres Diagramms optimieren, insbesondere bei langen oder komplexen Beschriftungen. Durch die Ausrichtung der Beschriftungen rechts, links, zentriert oder im Blocksatz können Sie eine ausgewogene und optisch ansprechende Anordnung der Beschriftungen entlang der Achse erzielen.

Mit Aspose.Words für .NET können Sie problemlos auf die Ausrichtungseigenschaft der Teilstrichbeschriftungen einer Diagrammachse zugreifen und diese ändern. So haben Sie die volle Kontrolle über die Darstellung und das Layout der Teilstrichbeschriftungen in den Diagrammen Ihres Word-Dokuments.

### FAQs

#### F1. Was sind mehrzeilige Beschriftungen mit Teilstrichen in einer Diagrammachse?
Mehrzeilige Häkchenbeschriftungen in einer Diagrammachse beziehen sich auf Achsenbeschriftungen, die sich über mehrere Zeilen erstrecken, wenn der Beschriftungstext lang ist oder umgebrochen werden muss, damit er in den verfügbaren Platz passt. Anstatt den Beschriftungstext abzuschneiden oder visuelle Unordnung zu verursachen, teilt die Diagrammachse die Beschriftungen automatisch in mehrere Zeilen auf, um die Lesbarkeit zu gewährleisten. Mehrzeilige Häkchenbeschriftungen sind besonders nützlich, wenn Sie mit langen Kategorie- oder Wertbeschriftungen in Diagrammen arbeiten.

#### F2. Kann ich die Ausrichtung der Teilstrichbeschriftungen in einer Diagrammachse anpassen?
 Ja, Sie können die Ausrichtung der Teilstrichbeschriftungen in einer Diagrammachse mit Aspose.Words für .NET anpassen. Durch Zugriff auf die`TickLabelAlignment` Eigentum der`ChartAxis` Objekt können Sie die gewünschte Ausrichtung für die Teilstrichbeschriftungen festlegen. Die Ausrichtungsoptionen umfassen links, rechts, zentriert oder Blocksatz. Durch Anpassen der Ausrichtung können Sie die horizontale Positionierung der Teilstrichbeschriftungen entlang der Diagrammachse steuern und so eine ordnungsgemäße Lesbarkeit und visuelle Darstellung sicherstellen.

#### F3. Wann sollte ich eine Änderung der Ausrichtung der Teilstrichbeschriftung in einer Diagrammachse in Betracht ziehen?
Das Ändern der Ausrichtung der Teilstrichbeschriftung in einer Diagrammachse ist sinnvoll, wenn Sie lange oder mehrzeilige Beschriftungen haben, die eine optimale Darstellung und Lesbarkeit erfordern. Durch Anpassen der Ausrichtung können Sie sicherstellen, dass die Beschriftungen richtig ausgerichtet und beabstandet sind, sodass Überlappungen oder Abschneiden vermieden werden. Erwägen Sie das Ändern der Ausrichtung der Teilstrichbeschriftung, wenn Sie Diagramme mit langen Kategorienamen oder ausführlichen Wertbeschriftungen oder in anderen Szenarien verwenden, in denen die Standardausrichtung nicht das gewünschte visuelle Erscheinungsbild bietet.

#### F4. Beeinflusst die Ausrichtung der Teilstrichbeschriftung die einzeiligen Beschriftungen einer Diagrammachse?
Nein, die Ausrichtungseigenschaft für Teilstrichbeschriftungen wirkt sich nicht auf einzeilige Beschriftungen in einer Diagrammachse aus. Sie ist speziell für mehrzeilige Beschriftungen konzipiert, die umbrochen oder geteilt werden müssen. Einzeilige Beschriftungen werden basierend auf den Standardausrichtungseinstellungen der Diagrammachse ausgerichtet. Die Ausrichtungseigenschaft für Teilstrichbeschriftungen gilt nur für Beschriftungen, die sich über mehrere Zeilen erstrecken, sodass Sie die Ausrichtung jeder Zeile innerhalb der mehrzeiligen Beschriftung steuern können.

#### F5. Kann ich die Teilstrichbeschriftungen für die X-Achse und die Y-Achse in einem Diagramm unterschiedlich ausrichten?
 Ja, Sie können die Teilstrichbeschriftungen für die X- und Y-Achse in einem Diagramm mit Aspose.Words für .NET unterschiedlich ausrichten. Die Eigenschaft zur Ausrichtung der Teilstrichbeschriftung ist für jede Diagrammachse spezifisch. Durch Zugriff auf die entsprechende`ChartAxis` Objekt für die X- oder Y-Achse können Sie die Ausrichtung der Teilstrichbeschriftung unabhängig voneinander auf unterschiedliche Werte festlegen. Dies bietet Ihnen die Flexibilität, Teilstrichbeschriftungen je nach Ihren spezifischen Anforderungen für jede Achse im Diagramm unterschiedlich auszurichten.