---
title: Quelle zusammenhalten
linktitle: Quelle zusammenhalten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente verbinden und anhängen und dabei den Quellinhalt mit dem Zieldokument zusammenhalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/keep-source-together/
---

Dieses Tutorial führt Sie durch die Verwendung der Funktion „Quelle zusammenhalten“ von Aspose.Words für .NET. Mit dieser Funktion können Sie mehrere Word-Dokumente zusammenfügen und anhängen, während der Inhalt des Quelldokuments zusammen mit dem Inhalt des Zieldokuments bleibt. 

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Words für .NET installiert. Sie können es von der Aspose-Website herunterladen oder über NuGet installieren.
2. Visual Studio oder eine andere C#-Entwicklungsumgebung.

## Schritt 1: Initialisieren der Dokumentverzeichnisse

 Zuerst müssen Sie den Pfad zu Ihrem Dokumentverzeichnis festlegen. Ändern Sie den Wert des`dataDir` Variable für den Pfad, in dem sich Ihre Dokumente befinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie die Quell- und Zieldokumente

Als nächstes müssen Sie die Quell- und Zieldokumente mit dem Aspose.Words laden`Document` Klasse. Aktualisieren Sie die Dateinamen in der`Document` Konstruktor entsprechend Ihren Dokumentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Schritt 3: Festlegen, dass das Quelldokument nach dem Inhalt des Zieldokuments angezeigt wird

 Um sicherzustellen, dass das Quelldokument unmittelbar nach dem Inhalt des Zieldokuments erscheint, müssen Sie die`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument, um`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Schritt 4: Festlegen der Absatzformatierung „Mit nächstem zusammenhalten“ für das Quelldokument

 Um die Absätze im Quelldokument zusammenzuhalten, können Sie jeden Absatz im Dokument durchlaufen und die`KeepWithNext`Eigentum an`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Schritt 5: Anhängen des Quelldokuments an das Zieldokument

 Nun können Sie das Quelldokument an das Zieldokument anhängen, indem Sie`AppendDocument` Methode der`Document` Klasse. Die`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anfügevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie das zusammengeführte Dokument abschließend mit der Funktion "Quelle zusammenhalten" über den`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Beispielquellcode für Keep Source Together mit Aspose.Words für .NET 

Hier ist der vollständige Quellcode für die Funktion „Quelle zusammenhalten“ in C# unter Verwendung von Aspose.Words für .NET:


```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Stellen Sie das Quelldokument so ein, dass es direkt nach dem Inhalt des Zieldokuments angezeigt wird.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Das ist es! Sie haben die Funktion „Quelle zusammenhalten“ erfolgreich mit Aspose.Words für .NET implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt, wobei die Absätze im Quelldokument zusammengehalten werden.