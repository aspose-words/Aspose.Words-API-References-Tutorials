---
title: Anderes Seiten-Setup
linktitle: Anderes Seiten-Setup
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument mit unterschiedlichen Seiteneinrichtungseinstellungen anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/different-page-setup/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Dokument mit unterschiedlichen Seiteneinstellungen an ein anderes Dokument anhängen. Der bereitgestellte Quellcode zeigt, wie Sie unterschiedliche Seiteneinstellungen für die Quell- und Zieldokumente einrichten und eine korrekte Fortsetzung und Nummerierung sicherstellen.

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

## Schritt 3: Seiteneinstellungen für das Quelldokument einrichten

 Passen Sie die Seiteneinstellungen des Quelldokuments an, um eine korrekte Fortsetzung und Nummerierung sicherzustellen. In diesem Beispiel setzen wir den Abschnittsanfang auf`SectionStart.Continuous`und die Seitennummerierung neu starten. Wir stellen außerdem sicher, dass Seitenbreite, -höhe und -ausrichtung mit dem letzten Abschnitt des Zieldokuments übereinstimmen.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Schritt 4: Absatzformatierung ändern

 Um die korrekte Formatierung beizubehalten, durchlaufen Sie alle Absätze im Quelldokument und setzen Sie die`KeepWithNext`Eigentum an`true`. Dadurch wird sichergestellt, dass die Absätze beim Anhängen zusammenbleiben.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Schritt 5: Anhängen des Quelldokuments an das Zieldokument

 Verwenden Sie die`AppendDocument` Methode des Zieldokuments, um das geänderte Quelldokument an das Zieldokument anzuhängen und dabei die Quellformatierung beizubehalten.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 6: Zieldokument speichern

Speichern Sie abschließend das geänderte Zieldokument mit dem`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments mit unterschiedlichen Seiteneinrichtungseinstellungen mit Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für verschiedene Seiteneinstellungen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Stellen Sie das Quelldokument so ein, dass es direkt nach dem Ende des Zieldokuments fortgesetzt wird.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Beginnen Sie die Seitennummerierung am Anfang des Quelldokuments neu.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//Um sicherzustellen, dass dies nicht passiert, wenn das Quelldokument andere Seiteneinstellungen hat, stellen Sie sicher, dass die
	// Die Einstellungen sind im letzten Abschnitt des Zieldokuments identisch.
	// Wenn im Quelldokument weitere zusammenhängende Abschnitte folgen,
	// Dies muss für diese Abschnitte wiederholt werden.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Durchlaufen Sie alle Abschnitte im Quelldokument.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```