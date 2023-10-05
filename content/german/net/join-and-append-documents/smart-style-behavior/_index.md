---
title: Intelligentes Stilverhalten
linktitle: Intelligentes Stilverhalten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie beim Zusammenfügen und Anhängen von Word-Dokumenten mit Aspose.Words für .NET ein intelligentes Stilverhalten beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/smart-style-behavior/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Smart Style Behavior-Funktion von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente verknüpfen und anhängen und dabei das intelligente Stilverhalten beibehalten.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Words für .NET installiert. Sie können es von der Aspose-Website herunterladen oder über NuGet installieren.
2. Visual Studio oder eine andere C#-Entwicklungsumgebung.

## Schritt 1: Initialisieren Sie die Dokumentverzeichnisse

 Zuerst müssen Sie den Pfad zu Ihrem Dokumentverzeichnis festlegen. Ändern Sie den Wert von`dataDir` Variable für den Pfad, in dem sich Ihre Dokumente befinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie die Quell- und Zieldokumente

 Als nächstes müssen Sie die Quell- und Zieldokumente mit Aspose.Words laden`Document` Klasse. Aktualisieren Sie die Dateinamen im`Document` Konstruktor entsprechend Ihren Dokumentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Fügen Sie einen Seitenumbruch in das Zieldokument ein

 Um sicherzustellen, dass der angehängte Inhalt auf einer neuen Seite im Zieldokument erscheint, können Sie mit a einen Seitenumbruch einfügen`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Schritt 4: Legen Sie die Verhaltensoptionen für intelligente Stile fest

Um das Smart-Style-Verhalten während des Anhängevorgangs zu aktivieren, müssen Sie eine Instanz von erstellen`ImportFormatOptions` und stellen Sie die ein`SmartStyleBehavior`Eigentum zu`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Schritt 5: Hängen Sie das Quelldokument an das Zieldokument an

 Jetzt können Sie das Quelldokument mit an das Zieldokument anhängen`InsertDocument` Methode der`DocumentBuilder` Klasse. Benutzen Sie die`ImportFormatMode.UseDestinationStyles` Parameter und übergeben Sie den`ImportFormatOptions` Objekt zur Aufrechterhaltung eines intelligenten Stilverhaltens.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit aktivierter Smart Style Behavior-Funktion mithilfe von`Save` Methode der`Document` Klasse.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Beispielquellcode für Smart Style Behavior mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Smart Style Behavior“ in C# mit Aspose.Words für .NET:
 
```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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

Das ist es! Sie haben die Smart Style Behavior-Funktion mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt unter Beibehaltung des intelligenten Stilverhaltens.