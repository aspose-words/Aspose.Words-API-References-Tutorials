---
title: Formatieren Sie die Anzahl der Datenbeschriftungen in einem Diagramm
linktitle: Formatieren Sie die Anzahl der Datenbeschriftungen in einem Diagramm
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Anzahl der Datenbeschriftungen in einem Diagramm mit Aspose.Words für .NET formatieren. Passen Sie ganz einfach Zahlenformate für Datenbeschriftungen an.
type: docs
weight: 10
url: /de/net/programming-with-charts/format-number-of-data-label/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die Anzahl der Datenbeschriftungen in einem Diagramm formatieren. Der bereitgestellte Quellcode zeigt, wie Sie ein Diagramm erstellen, Reihendaten hinzufügen und das Zahlenformat von Datenbeschriftungen anpassen.

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

 Fügen Sie als Nächstes mithilfe von ein Diagramm in das Dokument ein`InsertChart` Methode der`DocumentBuilder`. In diesem Beispiel fügen wir ein Liniendiagramm ein.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Schritt 3: Fügen Sie dem Diagramm Reihendaten hinzu

Fügen Sie dem Diagramm Seriendaten hinzu. In diesem Beispiel fügen wir drei Kategorien und ihre entsprechenden Werte hinzu.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Schritt 4: Passen Sie das Zahlenformat der Datenbeschriftungen an

 Um die Anzahl der Datenbeschriftungen zu formatieren, greifen Sie auf zu`DataLabels` Sammlung, die mit der Serie verbunden ist.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

In diesem Beispiel legen wir für jede Datenbeschriftung unterschiedliche Zahlenformate fest. Die erste Datenbeschriftung ist als Währung formatiert, die zweite als Datum und die dritte als Prozentsatz.

## Schritt 5: Speichern Sie das Dokument

 Speichern Sie abschließend das Dokument mit im angegebenen Verzeichnis`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Damit ist die Implementierung der Formatierung der Anzahl der Datenbeschriftungen in einem Diagramm mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für die Formatierung der Nummer des Datenetiketts mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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
	// Oder Sie können den Formatcode so festlegen, dass er mit einer Quellzelle verknüpft wird.
	//In diesem Fall wird NumberFormat auf „Allgemein“ zurückgesetzt und von einer Quellzelle geerbt.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie die Anzahl der Datenbeschriftungen in einem Diagramm mit Aspose.Words für .NET formatieren. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie ein Diagramm erstellen, Reihendaten hinzufügen und das Zahlenformat von Datenbeschriftungen entsprechend Ihren Anforderungen anpassen.

 Aspose.Words für .NET bietet eine umfassende API für die Textverarbeitung mit Diagrammen in Word-Dokumenten, sodass Sie verschiedene Aspekte des Diagramms, einschließlich Datenbeschriftungen, bearbeiten können. Durch den Zugriff auf`DataLabels` In einer mit einer Serie verknüpften Sammlung können Sie das Zahlenformat einzelner Datenbeschriftungen anpassen.

Mit der API können Sie die Anzeige von Werten steuern, unterschiedliche Zahlenformate für jede Datenbeschriftung festlegen und das Zahlenformat mit einer Quellzelle verknüpfen. Diese Flexibilität ermöglicht es Ihnen, numerische Daten in Diagrammen mit der gewünschten Formatierung darzustellen, z. B. Währungssymbole, Datumsformate und Prozentwerte.

Durch die Verwendung von Aspose.Words für .NET können Sie leistungsstarke Diagrammfunktionen in Ihre .NET-Anwendungen integrieren und professionell aussehende Dokumente mit vollständig formatierten Diagrammen und Datenbeschriftungen erstellen.

### FAQs

#### Q1. Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine funktionsreiche Dokumentverarbeitungsbibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert in .NET-Anwendungen zu erstellen, zu bearbeiten und zu speichern. Es bietet zahlreiche Funktionen für die Textverarbeitung mit Dokumentelementen, einschließlich Diagrammen und Datenbeschriftungen.

#### Q2. Wie kann ich Aspose.Words für .NET installieren?
Sie können Aspose.Words für .NET installieren, indem Sie es mithilfe des NuGet-Paketmanagers in Visual Studio herunterladen. Suchen Sie einfach im NuGet-Paketmanager nach „Apose.Words“ und installieren Sie es in Ihrem Projekt.

#### Q3. Kann ich andere Aspekte des Diagramms mit Aspose.Words für .NET formatieren?
Ja, Aspose.Words für .NET bietet umfangreiche Funktionen zum Formatieren verschiedener Aspekte eines Diagramms. Zusätzlich zu den Datenbeschriftungen können Sie Diagrammtyp, Reihendaten, Achseneigenschaften, Legende, Titel, Plotbereich und viele andere Elemente des Diagramms anpassen. Die API bietet eine detaillierte Kontrolle über die Darstellung und Formatierung von Diagrammen.

#### Q4. Kann ich unterschiedliche Zahlenformate auf unterschiedliche Datenbeschriftungen in derselben Serie anwenden?
Ja, mit Aspose.Words für .NET können Sie unterschiedliche Zahlenformate auf einzelne Datenbeschriftungen innerhalb derselben Serie anwenden. Durch den Zugriff auf`DataLabels` Sammlung, die einer Serie zugeordnet ist, können Sie festlegen`FormatCode` -Eigenschaft jeder Datenbeschriftung, um das gewünschte Zahlenformat anzugeben. Dadurch können Sie numerische Werte in verschiedenen Formaten innerhalb desselben Diagramms darstellen.

#### F5. Kann ich benutzerdefinierte Zahlenformate für Datenbeschriftungen verwenden?
 Ja, Aspose.Words für .NET unterstützt benutzerdefinierte Zahlenformate für Datenbeschriftungen. Sie können das gewünschte Zahlenformat festlegen, indem Sie das festlegen`FormatCode` Eigenschaft einer Datenbeschriftung in einen benutzerdefinierten Formatcode umwandeln. Dies gibt Ihnen die Flexibilität, eine Vielzahl von Zahlenformaten anzuwenden, beispielsweise Währungssymbole, Datumsformate, Prozentwerte und mehr.

#### F6. Kann ich das Diagramm mit formatierten Datenbeschriftungen in verschiedenen Formaten speichern?
Ja, mit Aspose.Words für .NET können Sie das Dokument mit dem Diagramm mit formatierten Datenbeschriftungen in verschiedenen Formaten wie DOCX, PDF, HTML und mehr speichern. Sie können je nach Ihren Anforderungen das passende Format auswählen und nutzen`Save` Methode der`Document` Objekt zum Speichern des Dokuments. Die formatierten Datenbeschriftungen bleiben im gespeicherten Dokument erhalten.