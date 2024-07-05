---
title: Flächendiagramm in ein Word-Dokument einfügen
linktitle: Flächendiagramm in ein Word-Dokument einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Flächendiagramm in ein Dokument einfügen. Fügen Sie Seriendaten hinzu und speichern Sie das Dokument mit dem Diagramm.
type: docs
weight: 10
url: /de/net/programming-with-charts/insert-area-chart/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Flächendiagramm in ein Dokument einfügen. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Dokument speichern.

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

 Verwenden Sie als nächstes die`InsertChart` Methode der`DocumentBuilder` , um ein Flächendiagramm in das Dokument einzufügen.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Schritt 3: Seriendaten zum Diagramm hinzufügen

Fügen Sie dem Diagramm Reihendaten hinzu. In diesem Beispiel fügen wir fünf Datenpunkte mit entsprechenden Daten und Werten hinzu.

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

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Damit ist die Implementierung zum Einfügen eines Flächendiagramms mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Einfügen eines Flächendiagramms mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET ein Flächendiagramm in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein neues Dokument erstellen, ein Flächendiagramm einfügen, Seriendaten hinzufügen und das Dokument mit dem Diagramm speichern.

Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Diagrammen in Word-Dokumenten. Mit nur wenigen Codezeilen können Sie professionell aussehende Flächendiagramme erstellen und diese nach Ihren Anforderungen anpassen. Flächendiagramme werden häufig verwendet, um die Größe und Trends von Daten im Zeitverlauf oder in Kategorien anzuzeigen.

Durch die Verwendung von Aspose.Words für .NET können Sie den Prozess der Dokumenterstellung mit Flächendiagrammen automatisieren und so Zeit und Aufwand bei der manuellen Dokumenterstellung sparen. Die Bibliothek bietet eine breite Palette an Diagrammtypen und Anpassungsoptionen, mit denen Sie optisch ansprechende und informative Diagramme in Ihren Word-Dokumenten erstellen können.

### FAQs

#### F1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Dokumentverarbeitungsbibliothek, mit der Entwickler Word-Dokumente programmgesteuert in .NET-Anwendungen erstellen, ändern und konvertieren können. Es bietet einen umfassenden Satz von APIs für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen, Absätzen, Tabellen und mehr.

#### F2. Wie installiere ich Aspose.Words für .NET?
Um Aspose.Words für .NET zu installieren, können Sie den NuGet-Paketmanager in Visual Studio verwenden, um die Bibliothek direkt in Ihr Projekt zu installieren. Suchen Sie einfach im NuGet-Paketmanager nach „Aspose.Words“ und installieren Sie das Paket.

#### F3. Kann ich das Erscheinungsbild des Flächendiagramms anpassen?
Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Erscheinungsbilds des Flächendiagramms anpassen. Sie können Eigenschaften wie Diagrammtitel, Serienfarbe, Achsenbeschriftungen und Diagrammflächenformatierung ändern. Die Bibliothek bietet eine Vielzahl von APIs, mit denen Sie die visuellen Elemente des Diagramms steuern und ein individuelles Erscheinungsbild erstellen können, das Ihren Anforderungen entspricht.

#### F4. Kann ich dem Flächendiagramm mehrere Reihen hinzufügen?
Ja, Sie können mit Aspose.Words für .NET mehrere Reihen zum Flächendiagramm hinzufügen. Jede Reihe stellt eine Reihe von Datenpunkten dar, die im Diagramm dargestellt werden. Sie können Reihen mit unterschiedlichen Datensätzen hinzufügen und jede Reihe einzeln anpassen, einschließlich Name, Datenpunkte und Erscheinungsbild.

#### F5. Kann ich das Dokument mit dem eingefügten Flächendiagramm in verschiedenen Formaten speichern?
 Ja, Aspose.Words für .NET ermöglicht es Ihnen, das Dokument mit dem eingefügten Flächendiagramm in verschiedenen Formaten wie DOCX, PDF, HTML und mehr zu speichern. Sie können das gewünschte Ausgabeformat entsprechend Ihren Anforderungen auswählen und das`Save` Methode der`Document` Objekt, um das Dokument zu speichern. Das eingefügte Flächendiagramm bleibt im gespeicherten Dokument erhalten.

#### F6. Kann ich die Daten und das Erscheinungsbild des Flächendiagramms nach dem Einfügen ändern?
Ja, nachdem Sie das Flächendiagramm in das Dokument eingefügt haben, können Sie seine Daten und sein Erscheinungsbild mithilfe der von Aspose.Words für .NET bereitgestellten APIs ändern. Sie können die Seriendaten aktualisieren, den Diagrammtyp ändern, Achseneigenschaften anpassen und Formatierungsoptionen anwenden, um dynamische und interaktive Diagramme in Ihren Word-Dokumenten zu erstellen.