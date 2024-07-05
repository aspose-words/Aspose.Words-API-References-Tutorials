---
title: Smart Style-Verhalten
linktitle: Smart Style-Verhalten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie beim Zusammenführen und Anhängen von Word-Dokumenten mit Aspose.Words für .NET das Smart-Style-Verhalten beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/smart-style-behavior/
---

Dieses Tutorial führt Sie durch die Verwendung der Smart Style Behavior-Funktion von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente verbinden und anhängen und dabei das Smart Style Behavior beibehalten.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Words für .NET installiert. Sie können es von der Aspose-Website herunterladen oder über NuGet installieren.
2. Visual Studio oder eine andere C#-Entwicklungsumgebung.

## Schritt 1: Initialisieren der Dokumentverzeichnisse

 Zuerst müssen Sie den Pfad zu Ihrem Dokumentverzeichnis festlegen. Ändern Sie den Wert des`dataDir` Variable für den Pfad, in dem sich Ihre Dokumente befinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie die Quell- und Zieldokumente

Als nächstes müssen Sie die Quell- und Zieldokumente mit dem Aspose.Words laden`Document` Klasse. Aktualisieren Sie die Dateinamen in der`Document` Konstruktor entsprechend Ihren Dokumentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Einfügen eines Seitenumbruchs im Zieldokument

 Um sicherzustellen, dass der angehängte Inhalt im Zieldokument auf einer neuen Seite erscheint, können Sie einen Seitenumbruch einfügen mit einem`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Schritt 4: Festlegen der Smart Style-Verhaltensoptionen

Um das Smart Style-Verhalten während der Anfügeoperation zu aktivieren, müssen Sie eine Instanz von`ImportFormatOptions` und legen Sie die`SmartStyleBehavior`Eigentum an`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Schritt 5: Anhängen des Quelldokuments an das Zieldokument

 Nun können Sie das Quelldokument an das Zieldokument anhängen, indem Sie`InsertDocument` Methode der`DocumentBuilder` Klasse. Verwenden Sie die`ImportFormatMode.UseDestinationStyles` Parameter und übergeben Sie den`ImportFormatOptions` Objekt, um ein intelligentes Stilverhalten beizubehalten.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie das zusammengeführte Dokument abschließend mit aktivierter Funktion „Smart Style Behavior“ über den`Save` Methode der`Document` Klasse.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Beispielquellcode für Smart Style Behavior mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Smart Style Behavior“ in C# mit Aspose.Words für .NET:
 
```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

Das ist es! Sie haben die Funktion „Smart Style Behavior“ erfolgreich mit Aspose.Words für .NET implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt unter Beibehaltung des Smart Style Behavior.