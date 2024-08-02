---
title: Omtrekrand toepassen
linktitle: Omtrekrand toepassen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een omtrekrand toepast op een tabel in Word met behulp van Aspose.Words voor .NET. Volg onze stapsgewijze handleiding voor de perfecte tabelopmaak.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/apply-outline-border/
---
## Invoering

In de tutorial van vandaag duiken we in de wereld van documentmanipulatie met Aspose.Words voor .NET. Concreet gaan we leren hoe we een omtrekrand kunnen toepassen op een tabel in een Word-document. Dit is een fantastische vaardigheid om in uw gereedschapskist te hebben als u vaak werkt met het automatisch genereren en formatteren van documenten. Laten we dus beginnen aan deze reis om uw tafels niet alleen functioneel, maar ook visueel aantrekkelijk te maken.

## Vereisten

Voordat we ingaan op de code, zijn er een paar dingen die je nodig hebt:

1.  Aspose.Words voor .NET: Aspose.Words voor .NET moet geïnstalleerd zijn. Je kunt het downloaden[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Een geschikte ontwikkelomgeving zoals Visual Studio.
3. Basiskennis van C#: Een fundamenteel begrip van C# zal u helpen de tutorial te volgen.

## Naamruimten importeren

Zorg er om te beginnen voor dat u de benodigde naamruimten importeert. Dit is cruciaal voor toegang tot de Aspose.Words-functionaliteiten.

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

Laten we het proces opsplitsen in eenvoudige, beheersbare stappen.

## Stap 1: Laad het document

Eerst moeten we het Word-document laden dat de tabel bevat die we willen opmaken.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
```

 In deze stap gebruiken we de`Document` klasse van Aspose.Words om een bestaand document te laden. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar uw document is opgeslagen.

## Stap 2: Toegang tot de tabel

Vervolgens moeten we toegang krijgen tot de specifieke tabel die we willen opmaken. 

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

 Hier,`GetChild` methode haalt de eerste tabel in het document op. De parameters`NodeType.Table, 0, true` Zorg ervoor dat we het juiste knooppunttype krijgen.

## Stap 3: Lijn de tabel uit

Laten we nu de tabel op de pagina centreren.

```csharp
table.Alignment = TableAlignment.Center;
```

Deze stap zorgt ervoor dat de tafel netjes gecentreerd staat, waardoor deze een professionele uitstraling krijgt.

## Stap 4: Wis bestaande grenzen

Voordat we nieuwe grenzen toepassen, moeten we eventuele bestaande grenzen opruimen.

```csharp
table.ClearBorders();
```

Het opruimen van de randen zorgt ervoor dat onze nieuwe randen netjes worden aangebracht, zonder dat oude stijlen zich ermee bemoeien.

## Stap 5: Stel de omtrekranden in

Laten we nu de groene omtrekranden op de tabel toepassen.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

 Elk randtype (links, rechts, boven, onder) wordt afzonderlijk ingesteld. We gebruiken`LineStyle.Single` voor een vaste lijn,`1.5` voor de lijndikte, en`Color.Green` voor de randkleur.

## Stap 6: Pas celschaduw toe

Om de tabel visueel aantrekkelijker te maken, vullen we de cellen met een lichtgroene kleur.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

 Hier,`SetShading` wordt gebruikt om een effen lichtgroene kleur op de cellen aan te brengen, waardoor de tafel opvalt.

## Stap 7: Bewaar het document

Sla ten slotte het gewijzigde document op.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Met deze stap slaat u uw document op met de toegepaste opmaak. Je kunt hem openklappen en de mooi opgemaakte tafel zien.

## Conclusie

En daar heb je het! Door deze stappen te volgen, hebt u met succes een omtrekrand toegepast op een tabel in een Word-document met behulp van Aspose.Words voor .NET. Deze tutorial behandelde het laden van het document, het openen van de tabel, het uitlijnen ervan, het opheffen van bestaande randen, het toepassen van nieuwe randen, het toevoegen van celarcering en ten slotte het opslaan van het document. 

Met deze vaardigheden kunt u de visuele presentatie van uw tabellen verbeteren, waardoor uw documenten professioneler en aantrekkelijker worden. Veel codeerplezier!

## Veelgestelde vragen

### Kan ik verschillende stijlen toepassen op elke rand van de tafel?  
 Ja, u kunt op elke rand verschillende stijlen en kleuren toepassen door de parameters in het aan te passen`SetBorder` methode.

### Hoe kan ik de breedte van de rand wijzigen?  
 U kunt de breedte wijzigen door de derde parameter in het`SetBorder` methode. Bijvoorbeeld,`1.5` stelt een breedte van 1,5 punt in.

### Is het mogelijk om schaduw toe te passen op individuele cellen?  
 Ja, u kunt arcering toepassen op individuele cellen door elke cel te openen en de`SetShading` methode.

### Kan ik andere kleuren gebruiken voor randen en schaduwen?  
 Absoluut! U kunt elke kleur gebruiken die beschikbaar is in de`System.Drawing.Color` klas.

### Hoe kan ik de tafel horizontaal uitlijnen?  
 De`table.Alignment = TableAlignment.Center;` regel in de code centreert de tabel horizontaal op de pagina.