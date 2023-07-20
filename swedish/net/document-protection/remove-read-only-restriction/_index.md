---
title: Ta bort skrivskyddad begränsning
linktitle: Ta bort skrivskyddad begränsning
second_title: Aspose.Words Document Processing API
description: Lär dig hur du tar bort skrivskyddet från ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-protection/remove-read-only-restriction/
---
den här handledningen kommer vi att leda dig genom stegen för att använda Aspose.Words for .NET skrivskyddad begränsningsborttagningsfunktion. Den här funktionen låter dig ta bort skrivskyddet från ett Word-dokument för att göra det redigerbart. Följ stegen nedan:

## Steg 1: Skapa dokumentet och ställa in skyddet

Börja med att skapa en instans av klassen Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Ställ in ett lösenord för dokumentet med egenskapen SetPassword() för WriteProtection-objektet:

Var noga med att ersätta "MyPassword" med det faktiska lösenordet du använde för att skydda dokumentet.

## Steg 2: Ta bort skrivskyddad begränsning

För att ta bort den skrivskyddade begränsningen, ställ in egenskapen ReadOnlyRecommended till false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Steg 3: Använd obegränsat skydd

Till sist, tillämpa obegränsat skydd med hjälp av Document-objektets Protect()-metod:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara dokumentet utan skrivskyddad begränsning.

### Exempel på källkod för Ta bort skrivskyddad begränsning med Aspose.Words för .NET

Här är den fullständiga källkoden för att ta bort den skrivskyddade begränsningen med Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Ange ett lösenord som är upp till 15 tecken långt.
doc.WriteProtection.SetPassword("MyPassword");

//Ta bort det skrivskyddade alternativet.
doc.WriteProtection.ReadOnlyRecommended = false;

// Använd skrivskydd utan något skydd.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Genom att följa dessa steg kan du enkelt ta bort den skrivskyddade begränsningen från ett Word-dokument med Aspose.Words för .NET.


## Slutsats

I den här handledningen lärde vi oss hur man tar bort skrivskyddet från ett Word-dokument med Aspose.Words för .NET. Genom att följa de angivna stegen kan du enkelt ta bort begränsningen och göra dokumentet redigerbart igen. Aspose.Words för .NET erbjuder en omfattande uppsättning funktioner för att hantera dokumentskydd och begränsningar, vilket ger dig flexibilitet och kontroll över säkerheten och redigeringsmöjligheterna i dina Word-dokument.

### FAQ's

#### F: Vad är skrivskyddet i Aspose.Words för .NET?

S: Den skrivskyddade begränsningen i Aspose.Words för .NET hänvisar till en funktion som låter dig ställa in ett Word-dokument som skrivskyddat, vilket hindrar användare från att göra några ändringar av innehållet eller formateringen. Denna begränsning hjälper till att skydda dokumentets integritet och säkerställer att det inte ändras av misstag eller av uppsåt.

#### F: Hur kan jag ta bort skrivskyddet med Aspose.Words för .NET?

S: För att ta bort skrivskyddet från ett Word-dokument med Aspose.Words för .NET kan du följa dessa steg:
1.  Skapa en instans av`Document` klass och ställ in ett lösenord för dokumentet med hjälp av`SetPassword` metod för`WriteProtection` objekt.
2.  Ställ in`ReadOnlyRecommended` egendom av`WriteProtection` invända mot`false` för att ta bort den skrivskyddade rekommendationen.
3.  Tillämpa obegränsat skydd på dokumentet med hjälp av`Protect` metod för`Document` objekt med`NoProtection` skyddstyp.
4.  Spara dokumentet utan skrivskyddad begränsning med hjälp av`Save` metod för`Document` objekt.

#### F: Kan jag ta bort skrivskyddet från ett Word-dokument utan ett lösenord?

S: Nej, du kan inte ta bort skrivskyddet från ett Word-dokument utan att ange rätt lösenord. Den skrivskyddade begränsningen är inställd av säkerhetsskäl, och att ta bort den utan lösenordet skulle undergräva syftet att skydda dokumentets integritet.

#### F: Kan jag ta bort skrivskyddet från ett Word-dokument med fel lösenord?

S: Nej, du kan inte ta bort skrivskyddet från ett Word-dokument med fel lösenord. Rätt lösenord måste anges för att ta bort skrivskyddet och göra dokumentet redigerbart igen. Detta säkerställer att endast behöriga användare med rätt lösenord kan ändra dokumentet.

#### F: Är det möjligt att ta bort andra typer av dokumentskydd med Aspose.Words för .NET?

S: Ja, Aspose.Words för .NET tillhandahåller olika metoder för att ta bort andra typer av dokumentskydd, såsom lösenordsskydd, formulärskydd eller begränsningar för dokumentredigering. Beroende på vilken typ av skydd som tillämpas på dokumentet kan du använda motsvarande metoder och egenskaper som tillhandahålls av Aspose.Words för att ta bort det specifika skyddet och göra dokumentet redigerbart.
