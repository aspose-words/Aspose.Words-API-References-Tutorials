---
title: Diagrammachsen in einem Word-Dokument ausblenden
linktitle: Diagrammachsen in einem Word-Dokument ausblenden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Diagrammachsen in einem Dokument mit Aspose.Words für .NET ausblenden. Blenden Sie die Achsen aus, um eine übersichtlichere und fokussiertere Diagrammanzeige zu erhalten.
type: docs
weight: 10
url: /de/net/programming-with-charts/hide-chart-axis/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET die Diagrammachsen in einem Dokument ausblenden. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und die Diagrammachsen ausblenden.

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

 Fügen Sie als nächstes ein Diagramm in das Dokument ein, indem Sie`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Säulendiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Seriendaten zum Diagramm hinzufügen

Fügen Sie dem Diagramm Reihendaten hinzu. In diesem Beispiel fügen wir fünf Elemente und ihre entsprechenden Werte hinzu.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Schritt 4: Die Diagrammachse ausblenden

 Um die Diagrammachse auszublenden, rufen Sie das`AxisY` des Diagramms und legen Sie die`Hidden`Eigentum an`true`.

```csharp
chart.AxisY.Hidden = true;
```

In diesem Beispiel verbergen wir die Y-Achse des Diagramms.

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Damit ist die Implementierung zum Ausblenden der Diagrammachsen mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Ausblenden der Diagrammachsen mit Aspose.Words für .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie die Diagrammachse in einem Word-Dokument mit Aspose.Words für .NET ausblenden. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein Diagramm erstellen, Seriendaten hinzufügen und die Diagrammachse ausblenden, um den gewünschten visuellen Effekt zu erzielen.

 Aspose.Words für .NET bietet eine umfassende API für die Textverarbeitung mit Diagrammen in Word-Dokumenten, mit der Sie verschiedene Aspekte des Diagramms bearbeiten können, einschließlich der Achseneigenschaften. Durch den Zugriff auf die`AxisY` des Diagramms können Sie die Y-Achse ausblenden, um sie aus der Diagrammvisualisierung zu entfernen.

Das Ausblenden der Diagrammachse kann nützlich sein, wenn Sie sich auf die Diagrammdaten konzentrieren möchten, ohne von den Achsenlinien und Beschriftungen abgelenkt zu werden. Dadurch wirkt das Diagramm klarer und minimalistischer.

Durch die Verwendung von Aspose.Words für .NET können Sie problemlos Diagrammfunktionen in Ihre .NET-Anwendungen integrieren und professionell aussehende Dokumente mit benutzerdefinierten Diagrammen und ausgeblendeten Diagrammachsen erstellen.

### FAQs

#### F1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Dokumentverarbeitungsbibliothek, mit der Entwickler Word-Dokumente programmgesteuert in .NET-Anwendungen erstellen, bearbeiten und speichern können. Es bietet eine breite Palette von Funktionen für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen und Diagrammachsen.

#### F2. Wie kann ich Aspose.Words für .NET installieren?
Sie können Aspose.Words für .NET installieren, indem Sie es mithilfe des NuGet-Paketmanagers in Visual Studio herunterladen. Suchen Sie einfach im NuGet-Paketmanager nach „Aspose.Words“ und installieren Sie es in Ihrem Projekt.

#### F3. Kann ich sowohl die X-Achse als auch die Y-Achse eines Diagramms ausblenden?
 Ja, Sie können sowohl die X-Achse als auch die Y-Achse eines Diagramms mit Aspose.Words für .NET ausblenden. Um die X-Achse auszublenden, können Sie auf die`AxisX` des Diagramms und legen Sie die`Hidden`Eigentum an`true` Um die Y-Achse auszublenden, können Sie auf die`AxisY` und legen Sie die`Hidden`Eigentum an`true`. Dadurch können Sie beide Achsen aus der Diagrammvisualisierung entfernen.

#### F4. Kann ich die Achse nach dem Ausblenden wieder anzeigen?
Ja, Sie können die Diagrammachse wieder anzeigen, nachdem Sie sie mit Aspose.Words für .NET ausgeblendet haben. Um eine ausgeblendete Achse anzuzeigen, setzen Sie einfach die`Hidden` Eigentum des entsprechenden`AxisX` oder`AxisY` Einwände erheben gegen`false`. Dadurch wird die Achse im Diagramm wieder sichtbar.

#### F5. Kann ich andere Eigenschaften der Diagrammachsen anpassen?
 Ja, Aspose.Words für .NET ermöglicht Ihnen die Anpassung verschiedener Eigenschaften der Diagrammachsen, wie Achsentitel, Beschriftungen, Linienfarbe und mehr. Durch den Zugriff auf die`AxisX` Und`AxisY` Eigenschaften des Diagramms können Sie Eigenschaften ändern wie`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`und viele andere. Dadurch erhalten Sie eine feine Kontrolle über das Aussehen und Verhalten der Diagrammachsen.

#### F6. Kann ich das Diagramm mit der ausgeblendeten Achse in verschiedenen Dateiformaten speichern?
 Ja, Aspose.Words für .NET ermöglicht es Ihnen, das Dokument mit dem Diagramm mit einer ausgeblendeten Achse in verschiedenen Dateiformaten wie DOCX, PDF, HTML und mehr zu speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und das`Save` Methode der`Document` Objekt, um das Dokument zu speichern. Die ausgeblendete Achse bleibt im gespeicherten Dokument erhalten.