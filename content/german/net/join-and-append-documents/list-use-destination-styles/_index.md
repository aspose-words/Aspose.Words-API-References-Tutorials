---
title: Liste der Zielstile
linktitle: Liste der Zielstile
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente zusammenführen und anhängen und dabei die Listenstile des Zieldokuments beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/list-use-destination-styles/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „Liste mit Zielformatvorlagen“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente zusammenfügen und anhängen, während Sie die Listenformatvorlagen des Zieldokuments verwenden.

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

## Schritt 3: Festlegen, dass das Quelldokument nach dem Zieldokument fortgesetzt wird

 Um sicherzustellen, dass der Inhalt des Quelldokuments nach dem Ende des Zieldokuments fortgesetzt wird, müssen Sie die`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument, um`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Schritt 4: Listenformatierung verwalten

Um die Listenformatierung zu handhaben, durchlaufen Sie jeden Absatz im Quelldokument und prüfen, ob es sich um ein Listenelement handelt. Wenn dies der Fall ist, vergleichen Sie die Listen-ID mit den vorhandenen Listen im Zieldokument. Wenn eine Liste mit derselben ID vorhanden ist, erstellen Sie eine Kopie der Liste im Quelldokument und aktualisieren das Listenformat des Absatzes, um die kopierte Liste zu verwenden.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Schritt 5: Anhängen des Quelldokuments an das Zieldokument

 Nun können Sie das Quelldokument an das Zieldokument anhängen, indem Sie`AppendDocument` Methode der`Document` Klasse. Die`ImportFormatMode.UseDestinationStyles` Der Parameter stellt sicher, dass während des Anfügevorgangs die Listenstile des Zieldokuments verwendet werden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Schritt 6: Speichern Sie das endgültige Dokument

Speichern Sie das zusammengeführte Dokument abschließend mit der Funktion Liste Zielformatvorlagen verwenden, die Sie über den`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Beispielquellcode für List Use Destination Styles mit Aspose.Words für .NET 

Hier ist der vollständige Quellcode für die Funktion „Liste mit Zielstilen“ in C# unter Verwendung von Aspose.Words für .NET:


```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Stellen Sie das Quelldokument so ein, dass es direkt nach dem Ende des Zieldokuments fortgesetzt wird.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Behalten Sie den Überblick über die erstellten Listen.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Überprüfen Sie, ob das Zieldokument bereits eine Liste mit dieser ID enthält. Wenn dies der Fall ist, kann dies
			// bewirkt, dass die beiden Listen zusammen ausgeführt werden. Erstellen Sie stattdessen eine Kopie der Liste im Quelldokument.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Zu dieser ID existiert bereits eine neu kopierte Liste. Rufen Sie die gespeicherte Liste ab.
				// und verwenden Sie es im aktuellen Absatz.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Fügen Sie dem Dokument eine Kopie dieser Liste hinzu und bewahren Sie sie zur späteren Bezugnahme auf.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Setzt die Liste dieses Absatzes auf die kopierte Liste.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Hängt das Quelldokument an das Ende des Zieldokuments an.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Das ist es! Sie haben die Funktion „Liste Zielformatvorlagen verwenden“ erfolgreich mit Aspose.Words für .NET implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt mit den Listenformatvorlagen aus dem Zieldokument.