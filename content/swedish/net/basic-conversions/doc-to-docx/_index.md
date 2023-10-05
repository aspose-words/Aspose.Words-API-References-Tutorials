---
title: Konvertera Doc till Docx
linktitle: Konvertera Doc till Docx
second_title: Aspose.Words Document Processing API
description: Lär dig hur du konverterar Word-dokument från .doc- till Docx-format med Aspose.Words för .NET. Steg-för-steg handledning med exempel på källkod.
type: docs
weight: 10
url: /sv/net/basic-conversions/doc-to-docx/
---

I den här handledningen kommer vi att gå igenom processen steg-för-steg för att använda Aspose.Words för .NET för att konvertera ett Word-dokument i .doc-format till Docx-format. Vi kommer att förklara den medföljande C#-källkoden och guida dig om hur du implementerar den i dina egna projekt.

 Till att börja med, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från[Aspose.Releases](https://releases.aspose.com/words/net/).

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

 Nu när du har initierat`Document` objekt kan du fortsätta med konverteringsprocessen. Aspose.Words för .NET tillhandahåller olika alternativ och inställningar för anpassning, men för en grundläggande konvertering krävs inga ytterligare parametrar.

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

### Vanliga frågor

#### F1: Vad är Aspose.Words för .NET?

Aspose.Words för .NET är ett kraftfullt dokumentbehandlingsbibliotek som låter utvecklare skapa, modifiera, konvertera och rendera Microsoft Word-dokument programmatiskt. Det ger omfattande stöd för olika Word-filformat, inklusive DOC och DOCX.

#### F2: Varför ska jag konvertera DOC till DOCX?

Att konvertera DOC till DOCX erbjuder flera fördelar. DOCX är det nyare filformatet som introducerats av Microsoft, och det erbjuder förbättrad kompatibilitet, bättre alternativ för dataåterställning och förbättrade säkerhetsfunktioner. Dessutom har DOCX-filer en mindre filstorlek jämfört med DOC-filer, vilket gör dem lättare att dela och lagra.

#### F3: Hur kan jag konvertera en DOC-fil till DOCX med Aspose.Words för .NET?

För att konvertera en DOC-fil till DOCX med Aspose.Words för .NET, kan du följa dessa steg:

 Installera Aspose.Words for .NET: Börja med att ladda ner och installera Aspose.Words for .NET från[Aspose.Releases](https://releases.aspose.com/words/net/) eller via NuGet.

Ladda DOC-filen: Använd klassen Document för att ladda DOC-filen i minnet.

Spara dokumentet som DOCX: Anropa metoden Spara för klassen Document, och specificera utdatafilformatet som DOCX.

Verifiera den konverterade filen: Öppna den konverterade DOCX-filen med ett kompatibelt program för att säkerställa att konverteringen lyckades.

#### F4: Finns det några specifika överväganden vid konvertering av DOC till DOCX?

Ja, det finns några saker att tänka på under konverteringsprocessen:

Dokumentformatering: Även om konverteringsprocessen strävar efter att behålla den ursprungliga formateringen, kan vissa variationer förekomma på grund av skillnader mellan DOC- och DOCX-formaten.

Funktioner som stöds: Aspose.Words för .NET stöder ett brett utbud av funktioner, men alla funktioner kanske inte är tillgängliga för konvertering från DOC till DOCX. 

#### F5: Kan jag konvertera DOCX tillbaka till DOC med Aspose.Words för .NET?

Ja, Aspose.Words för .NET ger möjlighet att konvertera DOCX-filer tillbaka till det äldre DOC-formatet. Du kan följa en liknande process som beskrivits tidigare, med lämpligt filformat specificerat under konverteringen.



