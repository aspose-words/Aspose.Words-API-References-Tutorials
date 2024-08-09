---
title: Schakel Lettertypevervanging uitschakelen in
linktitle: Schakel Lettertypevervanging uitschakelen in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u lettertypevervanging in Word-documenten kunt in- of uitschakelen met Aspose.Words voor .NET. Zorg ervoor dat uw documenten er op alle platforms consistent uitzien.
type: docs
weight: 10
url: /nl/net/working-with-fonts/enable-disable-font-substitution/
---
## Invoering

Bent u ooit in een situatie terechtgekomen waarin uw zorgvuldig gekozen lettertypen in een Word-document worden vervangen wanneer u ze op een andere computer bekijkt? Vervelend, toch? Dit gebeurt als gevolg van lettertypevervanging, een proces waarbij het systeem een ontbrekend lettertype vervangt door een beschikbaar lettertype. Maar maak je geen zorgen! Met Aspose.Words voor .NET kunt u eenvoudig lettertypevervanging beheren en controleren. In deze zelfstudie leiden we u door de stappen om lettertypevervanging in uw Word-documenten in of uit te schakelen, zodat uw documenten er altijd precies zo uitzien als u dat wilt.

## Vereisten

Voordat we in de stappen duiken, zorgen we ervoor dat je alles hebt wat je nodig hebt:

-  Aspose.Words voor .NET: Download de nieuwste versie[hier](https://releases.aspose.com/words/net/).
- Visual Studio: elke versie die .NET ondersteunt.
- Basiskennis van C#: dit zal u helpen de coderingsvoorbeelden te volgen.

## Naamruimten importeren

Om aan de slag te gaan, moet u ervoor zorgen dat de benodigde naamruimten in uw project zijn geïmporteerd. Voeg deze bovenaan uw C#-bestand toe:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Laten we het proces nu opsplitsen in eenvoudige, beheersbare stappen.

## Stap 1: Stel uw project in

Stel eerst een nieuw project in Visual Studio in en voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek. Als je dat nog niet hebt gedaan, download het dan van de[Aspose-website](https://releases.aspose.com/words/net/).

## Stap 2: Laad uw document

Laad vervolgens het document waarmee u wilt werken. Zo doe je het:

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap. Deze code laadt het document in het geheugen, zodat u het kunt manipuleren.

## Stap 3: Configureer lettertype-instellingen

 Laten we nu een`FontSettings` object om de instellingen voor lettertypevervanging te beheren:

```csharp
FontSettings fontSettings = new FontSettings();
```

## Stap 4: Stel de standaardlettertypevervanging in

Stel de standaardlettertypevervanging in op een lettertype naar keuze. Dit lettertype wordt gebruikt als het originele lettertype niet beschikbaar is:

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

In dit voorbeeld gebruiken we Arial als het standaardlettertype.

## Stap 5: Schakel lettertype-infovervanging uit

Om de vervanging van lettertype-info uit te schakelen, waardoor het systeem ontbrekende lettertypen niet vervangt door beschikbare lettertypen, gebruikt u de volgende code:

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## Stap 6: Pas lettertype-instellingen toe op het document

Pas nu deze instellingen toe op uw document:

```csharp
doc.FontSettings = fontSettings;
```

## Stap 7: Bewaar uw document

Sla ten slotte uw gewijzigde document op. Je kunt het in elk gewenst formaat opslaan. Voor deze zelfstudie slaan we deze op als PDF:

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## Conclusie

En daar heb je het! Door deze stappen te volgen, kunt u eenvoudig de vervanging van lettertypen in uw Word-documenten beheren met behulp van Aspose.Words voor .NET. Dit zorgt ervoor dat uw documenten de beoogde look en feel behouden, waar ze ook worden bekeken.

## Veelgestelde vragen

### Kan ik ter vervanging andere lettertypen dan Arial gebruiken?

 Absoluut! U kunt elk lettertype opgeven dat beschikbaar is op uw systeem door de lettertypenaam te wijzigen in het`DefaultFontName` eigendom.

### Wat gebeurt er als het opgegeven standaardlettertype niet beschikbaar is?

Als het standaardlettertype niet beschikbaar is, gebruikt Aspose.Words een systeemfallback-mechanisme om een geschikte vervanging te vinden.

### Kan ik lettertypevervanging opnieuw inschakelen nadat ik deze heb uitgeschakeld?

 Ja, u kunt de`Enabled` eigendom van`FontInfoSubstitution` terug naar`true` als u lettertypevervanging weer wilt inschakelen.

### Is er een manier om te controleren welke lettertypen worden vervangen?

Ja, Aspose.Words biedt methoden om lettertypevervanging te registreren en bij te houden, zodat u kunt zien welke lettertypen worden vervangen.

### Kan ik deze methode naast DOCX ook voor andere documentformaten gebruiken?

Zeker! Aspose.Words ondersteunt verschillende formaten en u kunt deze lettertype-instellingen op elk ondersteund formaat toepassen.