---
title: Toon bladwijzers verbergen in Word-document
linktitle: Toon bladwijzers verbergen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een specifieke bladwijzer in een Word-document kunt weergeven of verbergen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/show-hide-bookmarks/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Show Hide Bookmarks in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Met deze functie kunt u een specifieke bladwijzer in een Word-document weergeven of verbergen.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Het document laden

 Wij gebruiken de`Document` class om het bestaande document uit een bestand te laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Stap 2: Toon of verberg een specifieke bladwijzer

 Wij gebruiken de`ShowHideBookmarkedContent`functie om een specifieke bladwijzer in het document weer te geven of te verbergen. Deze functie neemt als parameters het document, de naam van de bladwijzer en een booleaanse waarde om aan te geven of de bladwijzer moet worden weergegeven of verborgen:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Stap 3: Het gewijzigde document opslaan

 Wij gebruiken de`Save` methode om het gewijzigde document in een bestand op te slaan:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Voorbeeldbroncode voor Show Hide Bookmarks met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om aan te tonen dat een specifieke bladwijzer wordt weergegeven of verborgen met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedContent-broncode

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{MERGEFIELD-bladwijzer}" = "true" "" ""}
            Field field = builder.InsertField("IF \"", null);
            builder.MoveTo(field.Start.NextSibling);
            builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
            builder.Write("\" = \"true\" ");
            builder.Write("\"");
            builder.Write("\"");
            builder.Write(" \"\"");

            Node currentNode = field.Start;
            bool flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.Run)
                    if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
                        flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
                currentNode = nextNode;
            }

            Node endNode = bm.BookmarkEnd;
            flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.FieldEnd)
                    flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
                endNode = currentNode;
                currentNode = nextNode;
            }

            doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });
        }
		
```
## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Show Hide Bookmarks van Aspose.Words voor .NET kunt gebruiken. We volgden een stapsgewijze handleiding om een specifieke bladwijzer in een document weer te geven of te verbergen.

### Veelgestelde vragen over het tonen van bladwijzers verbergen in een Word-document

#### Vraag: Kan ik meerdere bladwijzers in hetzelfde document weergeven of verbergen?

A: Ja, u kunt meerdere bladwijzers in hetzelfde document weergeven of verbergen door stap 2 en 3 te herhalen voor elke bladwijzer die u wilt verwerken.

#### Vraag: Werkt de meegeleverde code met andere Word-documentformaten, zoals .doc of .docm?

A: Ja, de meegeleverde code werkt met verschillende Word-documentformaten die worden ondersteund door Aspose.Words, zoals .doc en .docm. Zorg ervoor dat u de juiste bestandsnaam en het juiste pad gebruikt bij het laden en opslaan van het document.

#### Vraag: Hoe kan ik een verborgen bladwijzer weer weergeven?

 A: Om een verborgen bladwijzer opnieuw te tonen, moet u dezelfde gebruiken`ShowHideBookmarkedContent` functie die de waarde doorgeeft`true` voor de Booleaanse parameter die aangeeft of de bladwijzer moet worden weergegeven of verborgen.

#### Vraag: Kan ik voorwaarden gebruiken om bladwijzers weer te geven of te verbergen op basis van samenvoegveldwaarden in het document?

 A: Ja, u kunt voorwaarden gebruiken en veldwaarden samenvoegen om te bepalen of een bladwijzer moet worden weergegeven of verborgen. U kunt de code van de`ShowHideBookmarkedContent` functie om rekening te houden met de juiste omstandigheden en waarden.

#### Vraag: Hoe kan ik een bladwijzer in een Word-document verwijderen met Aspose.Words voor .NET?

 A: Om een bladwijzer in een Word-document te verwijderen met Aspose.Words voor .NET, kunt u de`RemoveBookmarks` werkwijze van de`Document` klas. Hier is een voorbeeldcode:

```csharp
doc.RemoveBookmarks("BookmarkName");
```