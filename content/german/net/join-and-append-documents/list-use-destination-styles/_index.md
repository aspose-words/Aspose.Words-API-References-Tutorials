---
title: Liste „Zielstile verwenden“ auflisten
linktitle: Liste „Zielstile verwenden“ auflisten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente zusammenfügen und anhängen und dabei die Listenstile des Zieldokuments beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/list-use-destination-styles/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „List Use Destination Styles“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente zusammenfügen und anhängen und dabei die Listenstile des Zieldokuments verwenden.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Words für .NET installiert. Sie können es von der Aspose-Website herunterladen oder über NuGet installieren.
2. Visual Studio oder eine andere C#-Entwicklungsumgebung.

## Schritt 1: Initialisieren Sie die Dokumentverzeichnisse

 Zuerst müssen Sie den Pfad zu Ihrem Dokumentverzeichnis festlegen. Ändern Sie den Wert von`dataDir`Variable für den Pfad, in dem sich Ihre Dokumente befinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie die Quell- und Zieldokumente

 Als nächstes müssen Sie die Quell- und Zieldokumente mit Aspose.Words laden`Document` Klasse. Aktualisieren Sie die Dateinamen im`Document` Konstruktor entsprechend Ihren Dokumentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Schritt 3: Stellen Sie das Quelldokument so ein, dass es nach dem Zieldokument fortfährt

 Um sicherzustellen, dass der Inhalt des Quelldokuments nach dem Ende des Zieldokuments fortgesetzt wird, müssen Sie Folgendes festlegen`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Schritt 4: Behandeln Sie die Listenformatierung

Um die Listenformatierung zu handhaben, durchlaufen Sie jeden Absatz im Quelldokument und prüfen, ob es sich um ein Listenelement handelt. Ist dies der Fall, vergleichen Sie die Listen-ID mit den vorhandenen Listen im Zieldokument. Wenn eine Liste mit derselben ID vorhanden ist, erstellen Sie eine Kopie der Liste im Quelldokument und aktualisieren das Listenformat des Absatzes, um die kopierte Liste zu verwenden.

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

## Schritt 5: Hängen Sie das Quelldokument an das Zieldokument an

 Jetzt können Sie das Quelldokument mit an das Zieldokument anhängen`AppendDocument` Methode der`Document` Klasse. Der`ImportFormatMode.UseDestinationStyles` Der Parameter stellt sicher, dass die Listenstile des Zieldokuments während des Anhängevorgangs verwendet werden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit aktivierter Funktion „Zielformate auflisten“ mithilfe von`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Beispielquellcode für List Use Destination Styles mit Aspose.Words für .NET 

Hier ist der vollständige Quellcode für die Funktion „List Use Destination Styles“ in C# mit Aspose.Words für .NET:


```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//Legen Sie fest, dass das Quelldokument direkt nach dem Ende des Zieldokuments fortgesetzt wird.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Behalten Sie den Überblick über die erstellten Listen.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Prüfen Sie, ob das Zieldokument bereits eine Liste mit dieser ID enthält. Wenn dies der Fall ist, dann kann dies der Fall sein
			//bewirkt, dass die beiden Listen zusammen ausgeführt werden. Erstellen Sie stattdessen eine Kopie der Liste im Quelldokument.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Für diese ID existiert bereits eine neu kopierte Liste. Rufen Sie die gespeicherte Liste ab.
				// und verwenden Sie es für den aktuellen Absatz.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Fügen Sie dem Dokument eine Kopie dieser Liste hinzu und bewahren Sie sie zum späteren Nachschlagen auf.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Setzen Sie die Liste dieses Absatzes auf die kopierte Liste.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Hängen Sie das Quelldokument an das Ende des Zieldokuments an.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Das ist es! Sie haben die Funktion „Liste verwenden Zielstile“ mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt mit den Listenstilen aus dem Zieldokument.