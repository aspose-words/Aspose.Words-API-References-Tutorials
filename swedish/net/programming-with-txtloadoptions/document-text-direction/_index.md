---
title: Dokumenttextriktning
linktitle: Dokumenttextriktning
second_title: Aspose.Words Document Processing API
description: Lär dig hur du anger textriktning i dina dokument med Aspose.Words för .NET. Förbättra displayen för höger-till-vänster-språk.
type: docs
weight: 10
url: /sv/net/programming-with-txtloadoptions/document-text-direction/
---

den här handledningen kommer vi att utforska C#-källkoden som tillhandahålls för funktionen "Document Text Direction" med Aspose.Words för .NET. Den här funktionen låter dig ange textriktningen i ett dokument, vilket är särskilt användbart för språk som skrivs från höger till vänster, som hebreiska eller arabiska.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Konfigurera uppladdningsalternativ

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 I det här steget konfigurerar vi alternativen för dokumentladdning. Vi skapar en ny`TxtLoadOptions` objekt och ställ in`DocumentDirection` egendom till`DocumentDirection.Auto`. Detta värde talar om för Aspose.Words att automatiskt bestämma textriktningen baserat på innehållet i dokumentet.

## Steg 3: Ladda dokumentet

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 I det här steget laddar vi dokumentet med hjälp av`Document` metod och skicka sökvägen till textfilen som ska laddas. Vi använder även de angivna laddningsalternativen.

## Steg 4: Manipulera stycket och visa textriktningen

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 I det här steget kommer vi åt första stycket i dokumentet med hjälp av`FirstSection` och`Body` egenskaper. Därefter kommer vi åt`ParagraphFormat.Bidi` egenskap för att få textriktningen för stycket. Vi visar sedan detta värde i konsolen.

## Steg 5: Spara dokumentet

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 I detta sista steg sparar vi det resulterande dokumentet i .docx-format med hjälp av`Save` metod och skicka sökvägen till utdatafilen.

Nu kan du köra källkoden för att ladda textdokumentet och bestämma textriktningen. Det resulterande dokumentet kommer att sparas i den angivna katalogen med namnet "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Exempel på källkod för funktionalitet för dokumenttextriktning med Aspose.Words för .NET.


```csharp

            
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Slutsats

I den här handledningen utforskade vi funktionen för dokumenttextriktning i Aspose.Words för .NET. Vi lärde oss hur man specificerar textens riktning i ett dokument, speciellt för språk som är skrivna från höger till vänster, som hebreiska eller arabiska.

Denna funktion är viktig för att säkerställa att texten visas korrekt i flerspråkiga dokument. Genom att använda lämpliga laddningsalternativ kan Aspose.Words automatiskt upptäcka textens riktning och tillämpa den på dokumentet.

Med Aspose.Words kan du enkelt manipulera textens riktning i dina dokument, vilket ger en smidig och intuitiv läsupplevelse för användarna.

Det är viktigt att notera att den här funktionen är särskilt användbar vid ordbehandling med språk som kräver specifik textriktning. Aspose.Words gör den här uppgiften enkel genom att tillhandahålla kraftfulla verktyg för att hantera textens riktning i dina dokument.

Kom ihåg att använda lämpliga laddningsalternativ, som att ställa in automatisk textriktning, för att få de resultat du vill ha i dina dokument.

Aspose.Words för .NET erbjuder många avancerade funktioner för dokumenthantering och generering. Genom att ytterligare utforska dokumentationen och exemplen som tillhandahålls av Aspose.Words kommer du att fullt ut kunna utnyttja funktionerna i detta kraftfulla bibliotek.

Så tveka inte att integrera dokumenttextriktning i dina Aspose.Words för .NET-projekt och dra nytta av dess fördelar för att skapa attraktiva och högkvalitativa flerspråkiga dokument.