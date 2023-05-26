---
title: Få skyddstyp
linktitle: Få skyddstyp
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder funktionen Get Protection Type i Aspose.Words för .NET för att fastställa skyddstypen för ett dokument.
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

I den här artikeln förklarade vi hur du använder funktionen Get Protection Type i Aspose.Words för .NET för att fastställa skyddstypen för ett dokument. Genom att följa de beskrivna stegen kommer du enkelt att kunna integrera denna funktionalitet i dina egna C#-projekt och effektivt manipulera skyddade dokument. Aspose.Words för .NET erbjuder stor flexibilitet

