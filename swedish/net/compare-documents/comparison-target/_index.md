---
title: Jämförelsemål
linktitle: Jämförelsemål
second_title: Aspose.Words Document Processing API
description: Lär dig jämför målfunktionen i Aspose.Words för .NET som låter dig jämföra dokument och skapa ett nytt dokument som innehåller de ändringar som gjorts.
type: docs
weight: 10
url: /sv/net/compare-documents/comparison-target/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder jämförelsemålfunktionen i Aspose.Words för .NET.

## Steg 1: Introduktion

Jämför målfunktionen i Aspose.Words för .NET låter dig jämföra två dokument och generera ett nytt dokument som innehåller ändringarna som gjorts i måldokumentet. Detta kan vara användbart för att spåra ändringar som görs mellan olika versioner av ett dokument.

## Steg 2: Sätta upp miljön

Innan du börjar måste du ställa in din utvecklingsmiljö för att fungera med Aspose.Words för .NET. Se till att du har Aspose.Words-biblioteket installerat och har ett lämpligt C#-projekt att bädda in koden i.

## Steg 3: Lägg till nödvändiga sammansättningar

För att använda funktionen för jämförelsemål i Aspose.Words för .NET måste du lägga till de nödvändiga sammansättningarna till ditt projekt. Se till att du har rätt referenser till Aspose.Words i ditt projekt.

```csharp
using Aspose.Words;
```

## Steg 4: Dokumentinitiering

I det här steget kommer vi att initiera två dokument för jämförelse. Du måste ange katalogsökvägen där dina dokument finns, samt namnet på källdokumentet.

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Initiering av dokument A för att jämföra.
Document docA = new Document(dataDir + "DocumentA.docx");

// Klona dokument A för att skapa en identisk kopia av dokument B.
Document docB = docA.Clone();
```

## Steg 5: Konfigurera jämförelsealternativ

det här steget kommer vi att konfigurera jämförelsealternativen för att specificera beteendet för jämförelsen. Alternativen inkluderar möjligheten att ignorera formatering, såväl som jämförelsemålet, som är alternativet "Visa ändringar i" i Microsoft Words dialogruta "Jämför dokument".

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Steg 6: Dokumentjämförelse

Nu ska vi jämföra dokumenten och generera resultatet i ett nytt dokument.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 De`Compare` metoden jämför dokument A med dokument B och sparar ändringarna i dokument A. Du kan ange användarnamn och datum för jämförelsen som referens.

### Exempel på källkod för jämförelsemål med Aspose.Words för .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Relaterar till Microsoft Word alternativet "Visa ändringar i" i dialogrutan "Jämför dokument".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Slutsats

I den här artikeln utforskade vi diff-målfunktionen i Aspose.Words för .NET. Med den här funktionen kan du jämföra två dokument och skapa ett nytt dokument som innehåller de ändringar som gjorts. Du kan använda denna kunskap för att spåra ändringar mellan olika versioner av dina dokument.

