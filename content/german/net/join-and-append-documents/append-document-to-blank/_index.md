---
title: Dokument an leeres Feld anhängen
linktitle: Dokument an leeres Feld anhängen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie in Aspose.Words für .NET ein Dokument an ein leeres Zieldokument anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/append-document-to-blank/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET den Inhalt eines Dokuments an ein leeres Zieldokument anhängen. Der bereitgestellte Quellcode zeigt, wie Sie ein neues Dokument erstellen, seinen Inhalt entfernen und dann das Quelldokument anhängen.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen von[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Neues Zieldokument erstellen

 Erstelle eine neue`Document` Objekt für das Zieldokument.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Schritt 3: Vorhandenen Inhalt aus dem Zieldokument entfernen

 Um ein sauberes Zieldokument zu gewährleisten, entfernen Sie alle vorhandenen Inhalte aus dem Dokument mit dem`RemoveAllChildren` Methode.

```csharp
dstDoc.RemoveAllChildren();
```

## Schritt 4: Anhängen des Quelldokuments an das Zieldokument

 Fügen Sie den Inhalt des Quelldokuments an das Zieldokument an, indem Sie`AppendDocument` Methode mit`ImportFormatMode.KeepSourceFormatting` Möglichkeit.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Zieldokument speichern

Speichern Sie abschließend das geänderte Zieldokument mit dem`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments an ein leeres Zieldokument mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Dokument an leeres Dokument anhängen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Das Zieldokument ist nicht leer, sodass vor dem angehängten Dokument häufig eine leere Seite angezeigt wird.
	// Dies liegt daran, dass das Basisdokument einen leeren Abschnitt hat und das neue Dokument auf der nächsten Seite begonnen wird.
	// Entfernen Sie vor dem Anhängen den gesamten Inhalt aus dem Zieldokument.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```