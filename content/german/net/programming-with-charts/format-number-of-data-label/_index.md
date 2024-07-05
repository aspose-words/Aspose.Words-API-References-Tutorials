---
title: Anzahl der Datenbeschriftungen in einem Diagramm formatieren
linktitle: Anzahl der Datenbeschriftungen in einem Diagramm formatieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Anzahl der Datenbeschriftungen in einem Diagramm mit Aspose.Words für .NET formatieren. Passen Sie Zahlenformate für Datenbeschriftungen einfach an.
type: docs
weight: 10
url: /de/net/programming-with-charts/format-number-of-data-label/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET die Anzahl der Datenbeschriftungen in einem Diagramm formatieren. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Zahlenformat der Datenbeschriftungen anpassen.

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

 Fügen Sie als nächstes ein Diagramm in das Dokument ein, indem Sie`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Liniendiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Schritt 3: Seriendaten zum Diagramm hinzufügen

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir drei Kategorien und die entsprechenden Werte hinzu.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Schritt 4: Anpassen des Zahlenformats von Datenbeschriftungen

 Um die Anzahl der Datenbeschriftungen zu formatieren, rufen Sie das`DataLabels` Sammlung im Zusammenhang mit der Serie.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

In diesem Beispiel legen wir für jede Datenbeschriftung ein anderes Zahlenformat fest. Die erste Datenbeschriftung ist als Währung formatiert, die zweite als Datum und die dritte als Prozentsatz.

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend im angegebenen Verzeichnis mit dem`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Damit ist die Implementierung der Formatierung der Anzahl der Datenbeschriftungen in einem Diagramm mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Formatieren der Nummer eines Datenlabels mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Standardmäßig generierte Serien löschen.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Oder Sie können Formatcode so setzen, dass er mit einer Quellzelle verknüpft wird.
	//in diesem Fall wird NumberFormat auf allgemein zurückgesetzt und aus einer Quellzelle übernommen.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie die Anzahl der Datenbeschriftungen in einem Diagramm mit Aspose.Words für .NET formatieren. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein Diagramm erstellen, Seriendaten hinzufügen und das Zahlenformat der Datenbeschriftungen entsprechend Ihren Anforderungen anpassen.

 Aspose.Words für .NET bietet eine umfassende API für die Textverarbeitung mit Diagrammen in Word-Dokumenten, mit der Sie verschiedene Aspekte des Diagramms bearbeiten können, einschließlich Datenbeschriftungen. Durch den Zugriff auf die`DataLabels` Sammlung, die einer Reihe zugeordnet ist, können Sie das Zahlenformat einzelner Datenbeschriftungen anpassen.

Mit der API können Sie die Anzeige von Werten steuern, unterschiedliche Zahlenformate für jede Datenbeschriftung festlegen und das Zahlenformat mit einer Quellzelle verknüpfen. Dank dieser Flexibilität können Sie numerische Daten in Diagrammen mit der gewünschten Formatierung darstellen, z. B. mit Währungssymbolen, Datumsformaten und Prozentwerten.

Durch die Verwendung von Aspose.Words für .NET können Sie leistungsstarke Diagrammfunktionen in Ihre .NET-Anwendungen integrieren und professionell aussehende Dokumente mit vollständig formatierten Diagrammen und Datenbeschriftungen erstellen.

### FAQs

#### F1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine funktionsreiche Dokumentverarbeitungsbibliothek, mit der Entwickler Word-Dokumente programmgesteuert in .NET-Anwendungen erstellen, bearbeiten und speichern können. Es bietet eine breite Palette von Funktionen für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen und Datenbeschriftungen.

#### F2. Wie kann ich Aspose.Words für .NET installieren?
Sie können Aspose.Words für .NET installieren, indem Sie es mithilfe des NuGet-Paketmanagers in Visual Studio herunterladen. Suchen Sie einfach im NuGet-Paketmanager nach „Aspose.Words“ und installieren Sie es in Ihrem Projekt.

#### F3. Kann ich andere Aspekte des Diagramms mit Aspose.Words für .NET formatieren?
Ja, Aspose.Words für .NET bietet umfangreiche Möglichkeiten zum Formatieren verschiedener Aspekte eines Diagramms. Zusätzlich zu den Datenbeschriftungen können Sie Diagrammtyp, Seriendaten, Achseneigenschaften, Legende, Titel, Plotbereich und viele andere Elemente des Diagramms anpassen. Die API bietet eine detaillierte Kontrolle über das Erscheinungsbild und die Formatierung des Diagramms.

#### F4. Kann ich unterschiedliche Zahlenformate auf unterschiedliche Datenbeschriftungen in derselben Reihe anwenden?
Ja, Aspose.Words für .NET ermöglicht es Ihnen, unterschiedliche Zahlenformate auf einzelne Datenbeschriftungen innerhalb derselben Serie anzuwenden. Durch den Zugriff auf die`DataLabels` Sammlung, die einer Serie zugeordnet ist, können Sie die`FormatCode` -Eigenschaft jeder Datenbeschriftung, um das gewünschte Zahlenformat anzugeben. Auf diese Weise können Sie numerische Werte in verschiedenen Formaten im selben Diagramm darstellen.

#### F5. Kann ich benutzerdefinierte Zahlenformate für Datenbeschriftungen verwenden?
 Ja, Aspose.Words für .NET unterstützt benutzerdefinierte Zahlenformate für Datenbeschriftungen. Sie können das gewünschte Zahlenformat angeben, indem Sie die`FormatCode` Eigenschaft einer Datenbeschriftung auf einen benutzerdefinierten Formatcode. Dies gibt Ihnen die Flexibilität, eine breite Palette von Zahlenformaten anzuwenden, z. B. Währungssymbole, Datumsformate, Prozentwerte und mehr.

#### F6. Kann ich das Diagramm mit formatierten Datenbeschriftungen in verschiedenen Formaten speichern?
Ja, Aspose.Words für .NET ermöglicht es Ihnen, das Dokument mit dem Diagramm mit formatierten Datenbeschriftungen in verschiedenen Formaten wie DOCX, PDF, HTML und mehr zu speichern. Sie können das geeignete Format basierend auf Ihren Anforderungen auswählen und das`Save` Methode der`Document` Objekt, um das Dokument zu speichern. Die formatierten Datenbeschriftungen bleiben im gespeicherten Dokument erhalten.