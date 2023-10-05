---
title: Halten Sie die Quelle zusammen
linktitle: Halten Sie die Quelle zusammen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente zusammenfügen und anhängen und dabei den Quellinhalt mit dem Zieldokument zusammenhalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/keep-source-together/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Keep Source Together-Funktion von Aspose.Words für .NET. Mit dieser Funktion können Sie mehrere Word-Dokumente zusammenfügen und anhängen und dabei den Inhalt des Quelldokuments zusammen mit dem Inhalt des Zieldokuments beibehalten. 

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Words für .NET installiert. Sie können es von der Aspose-Website herunterladen oder über NuGet installieren.
2. Visual Studio oder eine andere C#-Entwicklungsumgebung.

## Schritt 1: Initialisieren Sie die Dokumentverzeichnisse

 Zuerst müssen Sie den Pfad zu Ihrem Dokumentverzeichnis festlegen. Ändern Sie den Wert von`dataDir` Variable für den Pfad, in dem sich Ihre Dokumente befinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie die Quell- und Zieldokumente

 Als nächstes müssen Sie die Quell- und Zieldokumente mit Aspose.Words laden`Document` Klasse. Aktualisieren Sie die Dateinamen im`Document` Konstruktor entsprechend Ihren Dokumentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Schritt 3: Legen Sie fest, dass das Quelldokument nach dem Inhalt des Zieldokuments angezeigt wird

 Um sicherzustellen, dass das Quelldokument unmittelbar nach dem Inhalt des Zieldokuments angezeigt wird, müssen Sie Folgendes festlegen`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Schritt 4: Legen Sie die Absatzformatierung „Beim nächsten beibehalten“ für das Quelldokument fest

Um die Absätze im Quelldokument zusammenzuhalten, können Sie jeden Absatz im Dokument durchlaufen und festlegen`KeepWithNext`Eigentum zu`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Schritt 5: Hängen Sie das Quelldokument an das Zieldokument an

 Jetzt können Sie das Quelldokument mit an das Zieldokument anhängen`AppendDocument` Methode der`Document` Klasse. Der`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anhängevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit aktivierter Funktion „Quelle zusammenhalten“.`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Beispielquellcode für Keep Source Together mit Aspose.Words für .NET 

Hier ist der vollständige Quellcode für die Funktion „Quelle zusammenhalten“ in C# mit Aspose.Words für .NET:


```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Legen Sie fest, dass das Quelldokument direkt nach dem Inhalt des Zieldokuments angezeigt wird.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Das ist es! Sie haben die Keep Source Together-Funktion mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt, wobei die Absätze im Quelldokument zusammengehalten werden.