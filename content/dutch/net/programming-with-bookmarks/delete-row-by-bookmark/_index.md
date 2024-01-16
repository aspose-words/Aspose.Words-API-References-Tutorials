---
title: Rij verwijderen via bladwijzer in Word-document
linktitle: Rij verwijderen via bladwijzer in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabelrij verwijdert op basis van een specifieke bladwijzer in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/delete-row-by-bookmark/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Row By Bookmark kunt gebruiken in de Aspose.Words voor .NET-bibliotheek. Met deze functie kunt u een tabelrij verwijderen op basis van een specifieke bladwijzer in een Word-document.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: De bladwijzer ophalen

 Wij gebruiken de`Bookmarks` eigenschap van het documentbereik om de specifieke bladwijzer te krijgen die we willen gebruiken om de tabelrij te verwijderen:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Stap 2: De tabelrij verwijderen

 Wij gebruiken de`GetAncestor` methode om de`Row` typ het bovenliggende element van de bladwijzer. Vervolgens gebruiken we de`Remove` methode om de tabelrij te verwijderen:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Voorbeeldbroncode voor het verwijderen van rij per bladwijzer met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om te demonstreren hoe u een tabelrij verwijdert op basis van een specifieke bladwijzer met behulp van Aspose.Words voor .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Row By Bookmark van Aspose.Words voor .NET kunt gebruiken. We volgden een stapsgewijze handleiding om een tabelrij te verwijderen op basis van een specifieke bladwijzer in een document.

### Veelgestelde vragen over het verwijderen van rijen per bladwijzer in een Word-document

#### Vraag: Kan ik meerdere rijen verwijderen met dezelfde bladwijzer?

A: Ja, u kunt meerdere rijen verwijderen met dezelfde bladwijzer. U moet echter de logica in uw code verwerken om het aantal rijen te bepalen dat u wilt verwijderen en de benodigde aanpassingen aanbrengen in het verstrekte codefragment.

#### Vraag: Wat gebeurt er als de bladwijzer niet in het document bestaat?

A: Als de opgegeven bladwijzer niet in het document bestaat, retourneert het codefragment een nulwaarde voor het bladwijzerobject. Daarom moet u dit scenario in uw code verwerken door de juiste controles toe te voegen voordat u probeert de tabelrij te verwijderen.

#### Vraag: Is de Aspose.Words-bibliotheek gratis te gebruiken?

 A: De Aspose.Words-bibliotheek is een commerciële bibliotheek en u heeft mogelijk een geldige licentie nodig om deze in uw projecten te gebruiken. U kunt een bezoek brengen aan de[Aspose.Words voor .NET API-referenties](https://reference.aspose.com/words/net/) voor meer informatie over hun licentieopties en prijzen.

#### Vraag: Kan ik rijen verwijderen uit een tabel in een specifiek gedeelte van het Word-document?

A: Ja, u kunt rijen verwijderen uit een tabel in een specifiek gedeelte van een Word-document. U kunt het geleverde codefragment aanpassen om een specifieke sectie te targeten door het juiste bereik of de juiste bladwijzer binnen die sectie te gebruiken.