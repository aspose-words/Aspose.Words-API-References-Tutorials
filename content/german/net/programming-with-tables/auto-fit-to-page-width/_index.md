---
title: Automatisch an Seitenbreite anpassen
linktitle: Automatisch an Seitenbreite anpassen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle automatisch an die Seitenbreite in einem Word-Dokument anpassen.
type: docs
weight: 10
url: /de/net/programming-with-tables/auto-fit-to-page-width/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle automatisch an die Seitenbreite in einem Word-Dokument anpassen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, Tabellen in Word-Dokumenten programmgesteuert zu bearbeiten.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Dokument erstellen und konfigurieren
Um die Textverarbeitung mit der Tabelle zu starten, müssen wir ein Dokument erstellen und den Dokumentgenerator konfigurieren. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den Dokumentengenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Einfügen und Konfigurieren der Tabelle
Als Nächstes fügen wir eine Tabelle in das Dokument ein, deren Breite der halben Seitenbreite entspricht. Verwenden Sie den folgenden Code:

```csharp
// Fügen Sie die Tabelle ein und konfigurieren Sie ihre Breite
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Hier verwenden wir den Document Builder, um mit der Erstellung der Tabelle zu beginnen, Zellen einzufügen und die bevorzugte Breite der Tabelle auf 50 % der Seitenbreite festzulegen. Dann fügen wir Text in jede Zelle ein.

## Schritt 4: Speichern des geänderten Dokuments
Abschließend müssen wir das geänderte Dokument mit der an die Seitenbreite angepassten Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das geänderte Dokument
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.
  
### Beispielquellcode für die automatische Anpassung an die Seitenbreite mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Fügen Sie eine Tabelle mit einer Breite ein, die die halbe Seitenbreite einnimmt.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle automatisch an die Seitenbreite in einem Word-Dokument anpasst. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen in Ihren Word-Dokumenten programmgesteuert bearbeiten. Mit dieser Funktion können Sie die Breite der Tabelle dynamisch an die Seite anpassen und so ein professionelles und optisch ansprechendes Dokument anbieten.