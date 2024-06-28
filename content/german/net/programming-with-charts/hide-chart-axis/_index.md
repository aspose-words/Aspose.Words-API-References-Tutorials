---
title: Diagrammachse in einem Word-Dokument ausblenden
linktitle: Diagrammachse in einem Word-Dokument ausblenden
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Diagrammachse in einem Dokument ausblenden. Blenden Sie die Achse aus, um eine übersichtlichere und fokussiertere Diagrammanzeige zu erzielen.
type: docs
weight: 10
url: /de/net/programming-with-charts/hide-chart-axis/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Diagrammachse in einem Dokument ausblenden. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Diagrammachse ausblenden.

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

 Fügen Sie als Nächstes mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Säulendiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Reihendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir fünf Elemente und ihre entsprechenden Werte hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Schritt 4: Diagrammachse ausblenden

 Um die Diagrammachse auszublenden, greifen Sie auf zu`AxisY` Eigenschaft des Diagramms und legen Sie fest`Hidden`Eigentum zu`true`.

```csharp
chart.AxisY.Hidden = true;
```

In diesem Beispiel blenden wir die Y-Achse des Diagramms aus.

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Damit ist die Implementierung des Ausblendens der Diagrammachse mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Diagrammachse ausblenden mit Aspose.Words für .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET die Diagrammachse in einem Word-Dokument ausblenden. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein Diagramm erstellen, Reihendaten hinzufügen und die Diagrammachse ausblenden, um den gewünschten visuellen Effekt zu erzielen.

 Aspose.Words für .NET bietet eine umfassende API für die Textverarbeitung mit Diagrammen in Word-Dokumenten, mit der Sie verschiedene Aspekte des Diagramms, einschließlich Achseneigenschaften, bearbeiten können. Durch den Zugriff auf`AxisY` Eigenschaft des Diagramms können Sie die Y-Achse ausblenden, um sie aus der Diagrammvisualisierung zu entfernen.

Das Ausblenden der Diagrammachse kann nützlich sein, wenn Sie sich auf die Diagrammdaten konzentrieren möchten, ohne von den Achsenlinien und -beschriftungen abgelenkt zu werden. Es verleiht dem Diagramm ein klareres und minimalistischeres Erscheinungsbild.

Durch die Verwendung von Aspose.Words für .NET können Sie problemlos Diagrammfunktionen in Ihre .NET-Anwendungen integrieren und professionell aussehende Dokumente mit benutzerdefinierten Diagrammen und ausgeblendeten Diagrammachsen erstellen.

### FAQs

#### Q1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Dokumentverarbeitungsbibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert in .NET-Anwendungen zu erstellen, zu bearbeiten und zu speichern. Es bietet zahlreiche Funktionen für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen und Diagrammachsen.

#### Q2. Wie kann ich Aspose.Words für .NET installieren?
Sie können Aspose.Words für .NET installieren, indem Sie es mithilfe des NuGet-Paketmanagers in Visual Studio herunterladen. Suchen Sie einfach im NuGet-Paketmanager nach „Apose.Words“ und installieren Sie es in Ihrem Projekt.

#### Q3. Kann ich sowohl die X-Achse als auch die Y-Achse eines Diagramms ausblenden?
 Ja, Sie können mit Aspose.Words für .NET sowohl die X-Achse als auch die Y-Achse eines Diagramms ausblenden. Um die X-Achse auszublenden, können Sie auf die zugreifen`AxisX` Eigenschaft des Diagramms und legen Sie fest`Hidden`Eigentum zu`true` . Um die Y-Achse auszublenden, können Sie ebenfalls auf Folgendes zugreifen`AxisY` Eigenschaft und legen Sie die fest`Hidden`Eigentum zu`true`. Dadurch können Sie beide Achsen aus der Diagrammvisualisierung entfernen.

#### Q4. Kann ich die Achse wieder einblenden, nachdem ich sie ausgeblendet habe?
Ja, Sie können die Diagrammachse wieder anzeigen, nachdem Sie sie mit Aspose.Words für .NET ausgeblendet haben. Um eine ausgeblendete Achse anzuzeigen, legen Sie einfach fest`Hidden` Eigentum des entsprechenden`AxisX` oder`AxisY` widersprechen`false`. Dadurch wird die Achse im Diagramm wieder sichtbar.

#### F5. Kann ich andere Eigenschaften der Diagrammachse anpassen?
 Ja, mit Aspose.Words für .NET können Sie verschiedene Eigenschaften der Diagrammachse anpassen, z. B. Achsentitel, Beschriftungen, Linienfarbe und mehr. Durch den Zugriff auf`AxisX` Und`AxisY` Eigenschaften des Diagramms können Sie Eigenschaften wie ändern`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, und viele andere. Dadurch erhalten Sie eine detaillierte Kontrolle über das Erscheinungsbild und das Verhalten der Diagrammachse.

#### F6. Kann ich das Diagramm mit der ausgeblendeten Achse in verschiedenen Dateiformaten speichern?
 Ja, mit Aspose.Words für .NET können Sie das Dokument, das das Diagramm mit einer ausgeblendeten Achse enthält, in verschiedenen Dateiformaten wie DOCX, PDF, HTML und mehr speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und verwenden`Save` Methode der`Document` Objekt zum Speichern des Dokuments. Die ausgeblendete Achse bleibt im gespeicherten Dokument erhalten.