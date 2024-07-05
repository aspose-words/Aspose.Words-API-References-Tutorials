---
title: Dokument mit Builder einfügen
linktitle: Dokument mit Builder einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument am Ende eines anderen Dokuments einfügen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/insert-document-with-builder/
---

 In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Dokument in ein anderes Dokument einfügen können. Dabei wird das`DocumentBuilder` Klasse. Der bereitgestellte Quellcode zeigt, wie ein Dokument am Ende eines anderen Dokuments eingefügt wird, während die Quellformatierung erhalten bleibt.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen von[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Öffnen Sie die Quell- und Zieldokumente

 Öffnen Sie die Quell- und Zieldokumente mit dem`Document` Klassenkonstruktor. Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Initialisieren Sie den DocumentBuilder

 Erstellen Sie eine neue Instanz des`DocumentBuilder` Klasse und übergeben Sie das Zieldokument als Parameter.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Schritt 4: Positionieren Sie den DocumentBuilder

Beweg das`DocumentBuilder` bis zum Ende des Dokuments mit dem`MoveToDocumentEnd` Methode. Fügen Sie einen Seitenumbruch ein, um den vorhandenen Inhalt vom eingefügten Dokument zu trennen.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Schritt 5: Einfügen des Quelldokuments

 Verwenden Sie die`InsertDocument` Methode der`DocumentBuilder` Klasse, um das Quelldokument in das Zieldokument einzufügen. Stellen Sie den Importformatmodus auf`ImportFormatMode.KeepSourceFormatting` um die Quellformatierung beizubehalten.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 6: Speichern Sie das geänderte Dokument

Speichern Sie abschließend das geänderte Zieldokument mit dem`Save` Methode der`Document` Objekt.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Damit ist die Implementierung des Einfügens eines Dokuments in ein anderes Dokument mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Dokument mit Builder einfügen“ unter Verwendung von Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```