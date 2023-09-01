---
title: Treten Sie Continuous bei
linktitle: Treten Sie Continuous bei
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET zwei Dokumente kontinuierlich verbinden und dabei die Formatierung beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/join-continuous/
---

In diesem Tutorial wird erklärt, wie Sie zwei Dokumente kontinuierlich mit Aspose.Words für .NET verbinden. Der bereitgestellte Quellcode zeigt, wie man ein Dokument an das Ende eines anderen Dokuments anhängt und dabei die ursprüngliche Formatierung beibehält.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

-  Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen unter[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Öffnen Sie die Quell- und Zieldokumente

 Öffnen Sie die Quell- und Zieldokumente mit`Document` Klassenkonstruktor. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Kontinuierlichen Abschnittsstart einrichten

 Damit das Quelldokument direkt nach dem Inhalt des Zieldokuments angezeigt wird, legen Sie fest`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Schritt 4: Hängen Sie das Quelldokument an

Hängen Sie das Quelldokument mit an das Zieldokument an`AppendDocument` Methode der`Document` Klasse. Stellen Sie den Importformatmodus auf ein`ImportFormatMode.KeepSourceFormatting` um die ursprünglichen Stile aus dem Quelldokument beizubehalten.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Speichern Sie das geänderte Dokument

 Speichern Sie abschließend das geänderte Zieldokument mit`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Damit ist die Implementierung der kontinuierlichen Verbindung zweier Dokumente mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Join Continuous mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Lassen Sie das Dokument direkt nach dem Inhalt des Zieldokuments erscheinen.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Hängen Sie das Quelldokument mit den im Quelldokument gefundenen Originalstilen an.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```