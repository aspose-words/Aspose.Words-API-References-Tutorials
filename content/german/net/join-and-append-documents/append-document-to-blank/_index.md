---
title: Dokument an Leerzeichen anhängen
linktitle: Dokument an Leerzeichen anhängen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie in Aspose.Words für .NET ein Dokument an ein leeres Zieldokument anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/append-document-to-blank/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET den Inhalt eines Dokuments an ein leeres Zieldokument anhängen. Der bereitgestellte Quellcode zeigt, wie Sie ein neues Dokument erstellen, seinen Inhalt entfernen und dann das Quelldokument daran anhängen.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen unter[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Erstellen Sie ein neues Zieldokument

 Erstelle eine neue`Document` Objekt für das Zieldokument.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Schritt 3: Entfernen Sie vorhandenen Inhalt aus dem Zieldokument

 Um ein sauberes Zieldokument zu gewährleisten, entfernen Sie mithilfe von alle vorhandenen Inhalte aus dem Dokument`RemoveAllChildren` Methode.

```csharp
dstDoc.RemoveAllChildren();
```

## Schritt 4: Hängen Sie das Quelldokument an das Zieldokument an

 Hängen Sie den Inhalt des Quelldokuments mit an das Zieldokument an`AppendDocument` Methode mit`ImportFormatMode.KeepSourceFormatting` Möglichkeit.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Speichern Sie das Zieldokument

Speichern Sie abschließend das geänderte Zieldokument mit`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments an ein leeres Zieldokument mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Append Document To Blank mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Das Zieldokument ist nicht leer, was häufig dazu führt, dass vor dem angehängten Dokument eine leere Seite angezeigt wird.
	// Dies liegt daran, dass das Basisdokument einen leeren Abschnitt hat und das neue Dokument auf der nächsten Seite begonnen wird.
	// Entfernen Sie vor dem Anhängen sämtliche Inhalte aus dem Zieldokument.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```