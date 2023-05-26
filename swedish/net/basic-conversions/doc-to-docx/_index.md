---
title: Doc till Docx
linktitle: Doc till Docx
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar Word-dokument från .doc- till Docx-format med Aspose.Words för .NET. Steg-för-steg handledning med exempel på källkod.
type: docs
weight: 10
url: /sv/net/basic-conversions/doc-to-docx/
---

I den här handledningen kommer vi att gå igenom processen steg-för-steg för att använda Aspose.Words för .NET för att konvertera ett Word-dokument i .doc-format till Docx-format. Vi kommer att förklara den medföljande C#-källkoden och guida dig om hur du implementerar den i dina egna projekt.

Till att börja med, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Konfigurera utvecklingsmiljön

Innan du börjar koda, se till att du har en lämplig utvecklingsmiljö. Öppna Visual Studio eller din föredragna C# IDE och skapa ett nytt projekt.

## Steg 2: Lägga till referenser och importera namnområden

För att använda Aspose.Words för .NET måste du lägga till referenser till biblioteket i ditt projekt. Högerklicka på mappen Referenser i ditt projekt, välj "Lägg till referens" och bläddra till platsen där du installerade Aspose.Words for .NET-biblioteket. Välj lämplig version och klicka på "OK" för att lägga till referensen.

Importera sedan de nödvändiga namnrymden överst i din C#-fil:

```csharp
using Aspose.Words;
```

## Steg 3: Initiera dokumentobjektet

 I det här steget kommer du att initiera`Document` objekt med sökvägen till ditt källdokument i .doc-format. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska katalogsökvägen där ditt dokument finns, och`"Document.doc"` med namnet på ditt källdokument. Här är kodavsnittet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.doc");
```

## Steg 4: Konvertera dokumentet till Docx-format

 Nu när du har initierat`Document`objekt kan du fortsätta med konverteringsprocessen. Aspose.Words för .NET tillhandahåller olika alternativ och inställningar för anpassning, men för en grundläggande konvertering krävs inga ytterligare parametrar.

## Steg 5: Spara det konverterade dokumentet

 För att spara det konverterade dokumentet i Docx-format måste du anropa`Save` metod på`Document` objekt. Ange sökväg och filnamn för utdatadokumentet. I det här exemplet kommer vi att spara det som`"BaseConversions.DocToDocx.docx"`. Här är kodavsnittet:

```csharp
doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
```

Det är allt! Du har framgångsrikt konverterat ett Word-dokument i .doc-format till Docx-format med Aspose.Words för .NET.

### Exempel på källkod för Doc To Docx med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.doc");

	doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
	
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.




