---
title: Ontwar rijbladwijzers in Word-document
linktitle: Ontwar rijbladwijzers in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u geneste rijbladwijzers in een Word-document kunt ontwarren om specifieke rijen te verwijderen zonder andere bladwijzers te beïnvloeden.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/untangle-row-bookmarks/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Untangle Row Bookmarks in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Deze functie maakt het mogelijk om de uiteinden van bladwijzers van regels op dezelfde lijn te plaatsen als het begin van bladwijzers.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Het document laden

 Wij gebruiken de`Document` class om het bestaande document uit een bestand te laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Stap 2: Ontrafel lijnbladwijzers

 Wij gebruiken de`Untangle` functie om bladwijzers uit rijen te ontwarren. Deze functie voert de aangepaste taak uit om de bladwijzeruiteinden van regels op dezelfde regel te plaatsen als het begin van de bladwijzer:

```csharp
Untangle(doc);
```

## Stap 3: Regel per bladwijzer verwijderen

 Wij gebruiken de`DeleteRowByBookmark` functie om een specifieke rij te verwijderen via de bladwijzer:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Stap 4: Controleer de integriteit van andere bladwijzers

We verifiëren dat de andere bladwijzers niet beschadigd zijn door te controleren of het uiteinde van de bladwijzer nog aanwezig is:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Voorbeeldbroncode voor Untangle Row Bookmarks met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om bladwijzers van regels te ontwarren met behulp van Aspose.Words voor .NET:


```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Hiermee wordt de aangepaste taak uitgevoerd waarbij de rijbladwijzeruiteinden in dezelfde rij worden geplaatst als het begin van de bladwijzer.
	Untangle(doc);

	// Nu kunnen we eenvoudig rijen verwijderen via een bladwijzer zonder de bladwijzers van andere rijen te beschadigen.
	DeleteRowByBookmark(doc, "ROW2");

	// Dit is alleen bedoeld om te controleren of de andere bladwijzer niet beschadigd is.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Ontwar de broncode
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                // Haal de bovenliggende rij op van zowel de bladwijzer als het bladwijzereindknooppunt.
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                // Als beide rijen in orde zijn en het begin en einde van de bladwijzer zich in aangrenzende rijen bevinden,
                // verplaats het eindknooppunt van de bladwijzer naar het einde van de laatste alinea in de laatste cel van de bovenste rij.
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### DeleteRowByBookmark-broncode
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Untangle Row Bookmarks van Aspose.Words voor .NET kunt gebruiken. We hebben een stapsgewijze handleiding gevolgd om rijbladwijzers te ontwarren en een specifieke rij te verwijderen zonder andere bladwijzers te beschadigen.

### Veelgestelde vragen over het ontwarren van rijbladwijzers in een Word-document

#### Vraag: Werkt het ontcijferen van rijbladwijzers alleen met rijbladwijzers in tabellen?

A: Ja, de functie Rijbladwijzers ontwarren is speciaal ontworpen om rijbladwijzers in tabellen te ontwarren. Deze functie kan worden gebruikt om regelbladwijzers in arrays te verwerken en ervoor te zorgen dat de uiteinden van de bladwijzers zich op dezelfde regel bevinden als het begin van de bladwijzer.

#### Vraag: Wijzigt de functie Unscramble Line Bookmarks de inhoud van het originele document?

A: Ja, de functie Lijnbladwijzers ontwarren wijzigt het originele document door de uiteinden van lijnbladwijzers te verplaatsen, zodat ze op dezelfde lijn komen te staan als het begin van de bladwijzers. Zorg ervoor dat u een reservekopie van het document opslaat voordat u deze functie toepast.

#### Vraag: Hoe kan ik regelbladwijzers in mijn Word-document identificeren?

A: Rijbladwijzers worden doorgaans in tabellen gebruikt om specifieke secties te markeren. U kunt rijbladwijzers identificeren door door de bladwijzers in het document te bladeren en te controleren of de bladwijzers zich in tabelrijen bevinden.

#### Vraag: Is het mogelijk rijbladwijzers in niet-aangrenzende tabellen te ontwarren?

A: De functie Rijbladwijzers ontwarren, zoals gepresenteerd in dit artikel, is ontworpen om rijbladwijzers in aangrenzende tabellen te ontwarren. Om rijbladwijzers in niet-aangrenzende tabellen te ontwarren, kunnen aanvullende aanpassingen aan de code nodig zijn, afhankelijk van de structuur van het document.

#### Vraag: Welke andere manipulaties kan ik uitvoeren op rijbladwijzers nadat ze zijn ontrafeld?

A: Zodra de lijnbladwijzers zijn ontrafeld, kunt u indien nodig verschillende manipulaties uitvoeren. Dit kan het bewerken, verwijderen of toevoegen van inhoud aan regels met bladwijzers omvatten. Zorg ervoor dat u zorgvuldig omgaat met lijnbladwijzers om ongewenste gevolgen voor de rest van het document te voorkomen.