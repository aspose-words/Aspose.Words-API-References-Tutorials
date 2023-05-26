---
title: Skrivet åtkomst
linktitle: Skrivet åtkomst
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder maskinskriven åtkomst för att manipulera tabeller i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-node/typed-access/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur man använder funktionen Typad Access med Aspose.Words för .NET.

## Steg 1: Importera nödvändiga referenser
Innan du börjar, se till att du har importerat de nödvändiga referenserna för att använda Aspose.Words för .NET i ditt projekt. Detta inkluderar att importera Aspose.Words-biblioteket och lägga till de nödvändiga namnområdena till din källfil.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Steg 2: Skapa ett nytt dokument
 I det här steget kommer vi att skapa ett nytt dokument med hjälp av`Document` klass.

```csharp
Document doc = new Document();
```

## Steg 3: Gå till avsnittet och kroppen
För att komma åt tabellerna i dokumentet måste vi först komma åt avsnittet och dokumentets brödtext.

```csharp
Section section = doc.FirstSection;
Body body = section.Body;
```

## Steg 4: Snabb och maskinskriven åtkomst till tabeller
Nu när vi har huvuddelen av dokumentet kan vi använda snabb och maskinskriven åtkomst för att komma åt alla tabeller som finns i brödtexten.

```csharp
TableCollection tables = body.Tables;
```

## Steg 5: Bläddra bland tabeller
 Genom att använda en`foreach` loop kan vi gå igenom alla tabeller och utföra specifika operationer på varje tabell.

```csharp
foreach(Table table in tables)
{
     // Snabb och maskinskriven åtkomst till den första raden i tabellen.
     table.FirstRow?.Remove();

     // Snabb och maskinskriven åtkomst till den sista raden i tabellen.
     table.LastRow?.Remove();
}
```

det här exemplet tar vi bort den första och sista raden i varje tabell med den snabba och maskinskrivna åtkomsten som tillhandahålls av Aspose.Words.

### Exempel på källkod för maskinskriven åtkomst med Aspose.Words för .NET

```csharp
	Document doc = new Document();

	Section section = doc.FirstSection;
	Body body = section.Body;
	
	// Snabbskriven åtkomst till alla underordnade tabellnoder som finns i kroppen.
	TableCollection tables = body.Tables;

	foreach (Table table in tables)
	{
		// Snabbskriven åtkomst till den första raden i tabellen.
		table.FirstRow?.Remove();

		// Snabbskriven åtkomst till den sista raden i tabellen.
		table.LastRow?.Remove();
	}
            
```

Detta är en komplett exempelkod för maskinskriven åtkomst till tabeller med Aspose.Words för .NET. Var noga med att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera denna kod i ditt projekt.

---
