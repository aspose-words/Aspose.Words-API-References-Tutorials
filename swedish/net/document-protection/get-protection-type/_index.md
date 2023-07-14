---
title: Få skyddstyp i Word-dokument
linktitle: Få skyddstyp i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder funktionen Få skyddstyp i Word-dokument i Aspose.Words för .NET för att fastställa skyddstypen för ett dokument.
type: docs
weight: 10
url: /sv/net/document-protection/get-protection-type/
---
Välkommen till denna steg-för-steg-guide som förklarar C#-källkoden för funktionen Get Protection Type i Aspose.Words för .NET. I den här artikeln visar vi dig hur du använder den här kraftfulla funktionen för att fastställa ett dokuments skyddstyp. Dokumentskydd är viktigt för att säkerställa konfidentialitet och integritet för dina filer. Vi leder dig genom stegen som behövs för att integrera Aspose.Words för .NET och använda funktionen Get Protection Type.

## Steg 1: Ladda dokumentet

Det första steget för att använda funktionen Get Protection Type är att ladda upp dokumentet du vill arbeta med. Du kan göra detta med klassen Document som tillhandahålls av Aspose.Words för .NET. Här är en exempelkod för att ladda ett dokument från en fil:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

Var noga med att ange rätt sökväg till din dokumentfil.

## Steg 2: Hämta skyddstypen

Efter att dokumentet har laddats upp kan du använda egenskapen ProtectionType för dokumentobjektet för att hämta den typ av skydd som tillämpas på dokumentet. Så här kan du göra det:

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Exempel på källkod för Get Protection Type med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Get Protection Type med Aspose.Words för .NET:

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## Slutsats

den här artikeln förklarade vi hur du använder funktionen Get Protection Type i Aspose.Words för .NET för att fastställa skyddstypen för ett dokument. Genom att följa de beskrivna stegen kommer du enkelt att kunna integrera denna funktionalitet i dina egna C#-projekt och effektivt manipulera skyddade dokument. Aspose.Words för .NET erbjuder stor flexibilitet

### FAQ's

#### F: Vad är egenskapen ProtectionType i Aspose.Words för .NET?

 A: Den`ProtectionType` egenskap i Aspose.Words för .NET är en funktion som låter dig bestämma vilken typ av skydd som tillämpas på ett Word-dokument. Den ger information om nivån på dokumentskydd, till exempel om dokumentet är skyddat för kommentarer, ändringar, formulär eller andra typer av begränsningar.

#### F: Hur kan jag hämta skyddstypen för ett dokument med Aspose.Words för .NET?

S: För att hämta skyddstypen för ett dokument med Aspose.Words för .NET kan du följa dessa steg:
1.  Ladda dokumentet med hjälp av`Document` klass.
2.  Få tillgång till`ProtectionType`egendom av`Document` objekt för att hämta skyddstypen.

#### F: Kan jag avgöra om ett dokument är skyddat för formulär eller formulärfält med hjälp av egenskapen ProtectionType?

 S: Ja, du kan avgöra om ett dokument är skyddat för formulär eller formulärfält med hjälp av`ProtectionType` egendom i Aspose.Words för .NET. Om skyddstypen är inställd på`AllowOnlyFormFields`, indikerar det att dokumentet är skyddat och endast formulärfält kan redigeras.

#### F: Vilka andra skyddstyper kan ProtectionType-egendomen returnera?

 A: Den`ProtectionType` egendom i Aspose.Words för .NET kan returnera olika skyddstyper, inklusive:
- `NoProtection`: Dokumentet är inte skyddat.
- `AllowOnlyRevisions`: Dokumentet är skyddat och endast ändringar kan göras.
- `AllowOnlyComments`: Dokumentet är skyddat och endast kommentarer kan läggas till.
- `AllowOnlyFormFields`: Dokumentet är skyddat och endast formulärfält kan redigeras.
- `ReadOnly`: Dokumentet är skyddat och inställt som skrivskyddat.

#### F: Kan jag ändra skyddstypen för ett dokument med egenskapen ProtectionType?

 A: Nej, det`ProtectionType`egenskapen i Aspose.Words för .NET är en skrivskyddad egenskap. Det låter dig hämta den aktuella skyddstypen för ett dokument men ger inte direkta möjligheter att ändra skyddstypen. För att ändra skyddstypen måste du använda andra metoder och egenskaper som finns tillgängliga i`Document` klass, som t.ex`Protect` eller`Unprotect`.

#### F: Är det möjligt att skydda ett dokument med flera skyddstyper samtidigt?

S: Nej, Aspose.Words för .NET tillåter endast en skyddstyp att tillämpas på ett dokument åt gången. Du kan dock kombinera olika skyddstyper genom att aktivera skydd, ställa in en typ, inaktivera skydd och sedan aktivera det igen med en annan typ.

