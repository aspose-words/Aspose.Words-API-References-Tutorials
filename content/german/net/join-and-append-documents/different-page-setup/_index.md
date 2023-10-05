---
title: Andere Seiteneinrichtung
linktitle: Andere Seiteneinrichtung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument mit unterschiedlichen Seiteneinrichtungseinstellungen anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/different-page-setup/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Dokument mit unterschiedlichen Seiteneinrichtungseinstellungen an ein anderes Dokument anhängen. Der bereitgestellte Quellcode zeigt, wie Sie verschiedene Seiteneinstellungen für die Quell- und Zieldokumente einrichten und eine ordnungsgemäße Fortsetzung und Nummerierung sicherstellen.

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

## Schritt 3: Seiteneinstellungen für das Quelldokument einrichten

 Passen Sie die Seiteneinrichtungseinstellungen des Quelldokuments an, um eine ordnungsgemäße Fortsetzung und Nummerierung sicherzustellen. In diesem Beispiel setzen wir den Abschnittsanfang auf`SectionStart.Continuous` und starten Sie die Seitennummerierung neu. Wir stellen außerdem sicher, dass die Seitenbreite, -höhe und -ausrichtung mit dem letzten Abschnitt des Zieldokuments übereinstimmen.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Schritt 4: Absatzformatierung ändern

 Um die richtige Formatierung beizubehalten, durchlaufen Sie alle Absätze im Quelldokument und legen Sie fest`KeepWithNext`Eigentum zu`true`Dadurch wird sichergestellt, dass die Absätze während des Anhängevorgangs zusammenbleiben.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Schritt 5: Hängen Sie das Quelldokument an das Zieldokument an

 Benutzen Sie die`AppendDocument` -Methode des Zieldokuments, um das geänderte Quelldokument an das Zieldokument anzuhängen und dabei die Quellformatierung beizubehalten.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 6: Speichern Sie das Zieldokument

 Speichern Sie abschließend das geänderte Zieldokument mit`Save` Methode der`Document` Objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Damit ist die Implementierung des Anhängens eines Dokuments mit unterschiedlichen Seiteneinrichtungseinstellungen mithilfe von Aspose.Words für .NET abgeschlossen.

### Beispielquellcode für Different Page Setup mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Legen Sie fest, dass das Quelldokument direkt nach dem Ende des Zieldokuments fortgesetzt wird.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Beginnen Sie mit der Seitennummerierung am Anfang des Quelldokuments neu.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Um sicherzustellen, dass dies nicht passiert, wenn das Quelldokument unterschiedliche Seiteneinrichtungseinstellungen hat, stellen Sie sicher, dass
	// Die Einstellungen sind im letzten Abschnitt des Zieldokuments identisch.
	// Wenn im Quelldokument weitere fortlaufende Abschnitte folgen,
	//Dies muss für diese Abschnitte wiederholt werden.
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