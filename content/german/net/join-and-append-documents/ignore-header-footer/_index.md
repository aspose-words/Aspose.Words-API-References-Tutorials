---
title: Kopf- und Fußzeile ignorieren
linktitle: Kopf- und Fußzeile ignorieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument anhängen und dabei Kopf- und Fußzeileninhalte ignorieren.
type: docs
weight: 10
url: /de/net/join-and-append-documents/ignore-header-footer/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Dokument anhängen und dabei den Inhalt von Kopf- und Fußzeilen ignorieren. Der bereitgestellte Quellcode zeigt, wie Sie die Importformatoptionen einrichten, um Kopf- und Fußzeilen während des Anhängevorgangs auszuschließen.

## Schritt 1: Einrichten des Projekts

Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen von[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Öffnen Sie die Quell- und Zieldokumente

 Öffnen Sie die Quell- und Zieldokumente mit dem`Document` Klassenkonstruktor. Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Importformatoptionen einrichten

 Erstellen Sie eine Instanz des`ImportFormatOptions` Klasse und legen Sie die`IgnoreHeaderFooter`Eigentum an`false`. Dadurch wird sichergestellt, dass der Kopf- und Fußzeileninhalt beim Anhängen einbezogen wird.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Schritt 4: Anhängen des Quelldokuments an das Zieldokument

 Verwenden Sie die`AppendDocument` Methode des Zieldokuments, um das Quelldokument anzuhängen. Übergeben Sie`ImportFormatMode.KeepSourceFormatting`als zweiten Parameter und die Importformatoptionen als dritten Parameter.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Schritt 5: Zieldokument speichern

Speichern Sie abschließend das geänderte Zieldokument mit dem`Save` Methode der`Document` Objekt.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments unter Ignorieren des Kopf- und Fußzeileninhalts mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode zum Ignorieren von Kopf- und Fußzeilen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```