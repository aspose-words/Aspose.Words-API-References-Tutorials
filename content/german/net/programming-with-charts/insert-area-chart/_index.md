---
title: Flächendiagramm in ein Word-Dokument einfügen
linktitle: Flächendiagramm in ein Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Flächendiagramm in ein Dokument einfügen. Fügen Sie Seriendaten hinzu und speichern Sie das Dokument mit dem Diagramm.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-area-chart/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Flächendiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

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

 Als nächstes verwenden Sie die`InsertChart` Methode der`DocumentBuilder` um ein Flächendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Fügen Sie dem Diagramm Seriendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir fünf Datenpunkte mit entsprechenden Daten und Werten hinzu.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Schritt 4: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Damit ist die Implementierung des Einfügens eines Flächendiagramms mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Flächendiagramm einfügen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET ein Flächendiagramm in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Flächendiagramm einfügen, Reihendaten hinzufügen und das Dokument mit dem Diagramm speichern.

Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Diagrammen in Word-Dokumenten. Mit nur wenigen Codezeilen können Sie professionell aussehende Flächendiagramme erstellen und diese entsprechend Ihren Anforderungen anpassen. Flächendiagramme werden häufig verwendet, um die Größe und Trends von Daten im Zeitverlauf oder in Kategorien anzuzeigen.

Durch die Verwendung von Aspose.Words für .NET können Sie den Prozess der Dokumentenerstellung mit Flächendiagrammen automatisieren und so Zeit und Aufwand bei der manuellen Dokumentenerstellung sparen. Die Bibliothek bietet eine große Auswahl an Diagrammtypen und Anpassungsoptionen, sodass Sie optisch ansprechende und informative Diagramme in Ihren Word-Dokumenten erstellen können.

### FAQs

#### Q1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Dokumentverarbeitungsbibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert in .NET-Anwendungen zu erstellen, zu ändern und zu konvertieren. Es bietet einen umfassenden Satz von APIs für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen, Absätzen, Tabellen und mehr.

#### Q2. Wie installiere ich Aspose.Words für .NET?
Um Aspose.Words für .NET zu installieren, können Sie den NuGet-Paketmanager in Visual Studio verwenden, um die Bibliothek direkt in Ihrem Projekt zu installieren. Suchen Sie einfach im NuGet-Paketmanager nach „Aspose.Words“ und installieren Sie das Paket.

#### Q3. Kann ich das Erscheinungsbild des Flächendiagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Erscheinungsbilds des Flächendiagramms anpassen. Sie können Eigenschaften wie Diagrammtitel, Reihenfarbe, Achsenbeschriftungen und Diagrammbereichsformatierung ändern. Die Bibliothek bietet einen umfangreichen Satz an APIs, um die visuellen Elemente des Diagramms zu steuern und ein individuelles Erscheinungsbild zu erstellen, das Ihren Anforderungen entspricht.

#### Q4. Kann ich dem Flächendiagramm mehrere Reihen hinzufügen?
Ja, Sie können mit Aspose.Words für .NET mehrere Reihen zum Flächendiagramm hinzufügen. Jede Reihe stellt eine Reihe von Datenpunkten dar, die im Diagramm dargestellt werden. Sie können Serien mit unterschiedlichen Datensätzen hinzufügen und jede Serie individuell anpassen, einschließlich ihres Namens, ihrer Datenpunkte und ihres Erscheinungsbilds.

#### F5. Kann ich das Dokument mit dem eingefügten Flächendiagramm in verschiedenen Formaten speichern?
 Ja, mit Aspose.Words für .NET können Sie das Dokument mit dem eingefügten Flächendiagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und verwenden`Save` Methode der`Document` Objekt zum Speichern des Dokuments. Das eingefügte Flächendiagramm bleibt im gespeicherten Dokument erhalten.

#### F6. Kann ich die Daten und das Erscheinungsbild des Flächendiagramms nach dem Einfügen ändern?
Ja, nachdem Sie das Flächendiagramm in das Dokument eingefügt haben, können Sie dessen Daten und Aussehen mithilfe der von Aspose.Words für .NET bereitgestellten APIs ändern. Sie können die Reihendaten aktualisieren, den Diagrammtyp ändern, Achseneigenschaften anpassen und Formatierungsoptionen anwenden, um dynamische und interaktive Diagramme in Ihren Word-Dokumenten zu erstellen.