---
title: Upptäck numrering med blanksteg
linktitle: Upptäck numrering med blanksteg
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du upptäcker listnummer med blanksteg i Aspose.Words för .NET. Förbättra strukturen på dina dokument med lätthet.
type: docs
weight: 10
url: /sv/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
den här handledningen kommer vi att utforska C#-källkoden som tillhandahålls för funktionen "Detektering av numrering med blanksteg" med Aspose.Words för .NET. Den här funktionen låter dig upptäcka och skapa listor från ett textdokument som innehåller listnummer följt av blanksteg.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Skapa textdokumentet

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

I det här steget skapar vi en textsträng som simulerar ett textdokument som innehåller listnummer följt av blanksteg. Vi använder olika listavgränsare som punkt, höger parentes, punktsymbol och blanksteg.

## Steg 3: Konfigurera uppladdningsalternativ

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 I det här steget konfigurerar vi alternativen för dokumentladdning. Vi skapar en ny`TxtLoadOptions` objekt och ställ in`DetectNumberingWithWhitespaces` egendom till`true`. Detta gör att Aspose.Words kan upptäcka listnummer även om de följs av blanksteg.

## Steg 4: Ladda dokumentet och spara

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 I det här steget laddar vi dokumentet med den angivna textsträngen och laddningsalternativ. Vi använder a`MemoryStream` för att konvertera textsträngen till en minnesström. Sedan sparar vi det resulterande dokumentet i .docx-format.

### Exempel på källkod för White Space Numbering Detection-funktionen med Aspose.Words för .NET.

```csharp

            
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Skapa ett klartextdokument i form av en sträng med delar som kan tolkas som listor.
// Vid laddning kommer de tre första listorna alltid att upptäckas av Aspose.Words,
// och Listobjekt kommer att skapas för dem efter laddning.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// Den fjärde listan, med blanksteg mellan listnumret och listobjektets innehåll,
// kommer bara att upptäckas som en lista om "DetectNumberingWithWhitespaces" i ett LoadOptions-objekt är satt till true,
// för att undvika att stycken som börjar med siffror av misstag upptäcks som listor.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Ladda dokumentet medan du använder LoadOptions som en parameter och verifiera resultatet.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Nu kan du köra källkoden för att ladda textdokumentet som innehåller listnummer med blanksteg, och sedan skapa ett .docx-dokument med de upptäckta listorna. Utdatafilen kommer att sparas i den angivna katalogen med namnet "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Slutsats
I den här handledningen utforskade vi funktionen för upptäckt av blankstegsnumrering i Aspose.Words för .NET. Vi lärde oss hur man skapar listor från ett textdokument som innehåller listnummer följt av blanksteg.

Den här funktionen är extremt användbar för att behandla dokument som innehåller listnummer formaterade på olika sätt. Genom att använda lämpliga laddningsalternativ kan Aspose.Words upptäcka dessa listnummer, även om de följs av blanksteg, och konvertera dem till strukturerade listor i det slutliga dokumentet.

Genom att använda den här funktionen kan du spara tid och förbättra ditt arbetsflöde. Du kan enkelt extrahera information från textdokument och konvertera dem till välstrukturerade dokument med ordentliga listor.

Kom ihåg att överväga laddningsalternativ, som att konfigurera detektering av blankstegsuppringning, för att uppnå önskat resultat.

Aspose.Words för .NET erbjuder många avancerade funktioner för dokumenthantering och generering. Genom att ytterligare utforska dokumentationen och exemplen som tillhandahålls av Aspose.Words kommer du att fullt ut kunna utnyttja funktionerna i detta kraftfulla bibliotek.

Så tveka inte att integrera blankstegsnumrering i dina Aspose.Words för .NET-projekt och dra nytta av dess fördelar för att skapa välstrukturerade och läsbara dokument.


