---
title: Kopf- und Fußzeile ignorieren
linktitle: Kopf- und Fußzeile ignorieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument anhängen und dabei Kopf- und Fußzeileninhalte ignorieren.
type: docs
weight: 10
url: /de/net/join-and-append-documents/ignore-header-footer/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Dokument anhängen und dabei den Inhalt der Kopf- und Fußzeile ignorieren. Der bereitgestellte Quellcode zeigt, wie die Importformatoptionen eingerichtet werden, um die Kopf- und Fußzeile während des Anhängevorgangs auszuschließen.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen unter[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Öffnen Sie die Quell- und Zieldokumente

 Öffnen Sie die Quell- und Zieldokumente mit`Document` Klassenkonstruktor. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Importformatoptionen einrichten

 Erstellen Sie eine Instanz von`ImportFormatOptions` Klasse und legen Sie die fest`IgnoreHeaderFooter` Eigentum zu`false`. Dadurch wird sichergestellt, dass der Inhalt der Kopf- und Fußzeile beim Anhängevorgang einbezogen wird.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Schritt 4: Hängen Sie das Quelldokument an das Zieldokument an

 Benutzen Sie die`AppendDocument` Methode des Zieldokuments, um das Quelldokument anzuhängen. Passieren`ImportFormatMode.KeepSourceFormatting` als zweiten Parameter und die Importformatoptionen als dritten Parameter.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Schritt 5: Speichern Sie das Zieldokument

 Speichern Sie abschließend das geänderte Zieldokument mit`Save` Methode der`Document` Objekt.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments unter Ignorieren des Kopf- und Fußzeileninhalts mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für „Kopfzeile und Fußzeile ignorieren“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```