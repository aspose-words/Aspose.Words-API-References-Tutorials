---
title: Dokument anhängen
linktitle: Dokument anhängen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Inhalt eines Dokuments an ein anderes anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/append-document/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET den Inhalt eines Dokuments an ein anderes anhängen. Der bereitgestellte Quellcode zeigt, wie Sie die Quell- und Zieldokumente öffnen, Abschnitte aus dem Quelldokument importieren und an das Zieldokument anhängen.

## Schritt 1: Richten Sie das Projekt ein

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Aspose.Words für .NET-Bibliothek installiert. Sie können es herunterladen unter[Aspose.Releases]https://releases.aspose.com/words/net/ oder verwenden Sie den NuGet-Paketmanager, um es zu installieren.
- Ein Dokumentverzeichnispfad, in dem sich die Quell- und Zieldokumente befinden.

## Schritt 2: Öffnen Sie die Quell- und Zieldokumente

 Öffnen Sie die Quell- und Zieldokumente mit`Document` Klassenkonstruktor. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Abschnitte aus dem Quelldokument an das Zieldokument anhängen

 Durchlaufen Sie alle Abschnitte im Quelldokument und importieren Sie jeden Abschnitt mithilfe von in das Zieldokument`ImportNode` Methode. Hängen Sie dann den importierten Abschnitt an das Zieldokument an.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Schritt 4: Speichern Sie das Zieldokument

 Speichern Sie abschließend das geänderte Zieldokument mit`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Append Document mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Durchlaufen Sie alle Abschnitte im Quelldokument.
	// Abschnittsknoten sind unmittelbare untergeordnete Elemente des Dokumentknotens, sodass wir das Dokument einfach aufzählen können.
	foreach (Section srcSection in srcDoc)
	{
		// Da wir einen Abschnitt von einem Dokument in ein anderes kopieren,
		// Es ist erforderlich, den Abschnittsknoten in das Zieldokument zu importieren.
		// Dadurch werden alle dokumentspezifischen Verweise auf Stile, Listen usw. angepasst.
		//
		// Durch das Importieren eines Knotens wird eine Kopie des ursprünglichen Knotens erstellt, jedoch die Kopie
		// ss bereit zum Einfügen in das Zieldokument.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Nun kann der neue Abschnittsknoten an das Zieldokument angehängt werden.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```