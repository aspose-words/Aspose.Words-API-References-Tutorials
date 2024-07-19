---
title: Stel lettertype-fallback-instellingen in
linktitle: Stel lettertype-fallback-instellingen in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Font Fallback-instellingen in Aspose.Words voor .NET instelt. Deze uitgebreide handleiding zorgt ervoor dat alle tekens in uw documenten correct worden weergegeven.
type: docs
weight: 10
url: /nl/net/working-with-fonts/set-font-fallback-settings/
---

Wanneer u werkt met documenten die diverse tekstelementen bevatten, zoals verschillende talen of speciale tekens, is het van cruciaal belang ervoor te zorgen dat deze elementen correct worden weergegeven. Aspose.Words voor .NET biedt een krachtige functie genaamd Font Fallback Settings, die helpt bij het definiëren van regels voor het vervangen van lettertypen wanneer het originele lettertype bepaalde tekens niet ondersteunt. In deze handleiding onderzoeken we in een stapsgewijze zelfstudie hoe u Font Fallback-instellingen kunt instellen met Aspose.Words voor .NET.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Basiskennis van C#: Bekendheid met de programmeertaal C# en het .NET-framework.
-  Aspose.Words voor .NET: downloaden en installeren vanaf de[download link](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: Een opstelling zoals Visual Studio om uw code te schrijven en uit te voeren.
-  Voorbeelddocument: zorg dat u een voorbeelddocument hebt (bijv.`Rendering.docx`) klaar om te testen.
- XML voor lettertype-fallback-regels: bereid een XML-bestand voor waarin de fallback-regels voor lettertypen worden gedefinieerd.

## Naamruimten importeren

Om Aspose.Words te gebruiken, moet u de benodigde naamruimten importeren. Dit geeft toegang tot verschillende klassen en methoden die nodig zijn voor documentverwerking.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Stap 1: Definieer de documentmap

Definieer eerst de map waarin uw document is opgeslagen. Dit is essentieel voor het lokaliseren en verwerken van uw document.

```csharp
// Het pad naar de documentenmap
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het document

 Laad uw document in een Aspose.Words`Document` voorwerp. Met deze stap kunt u programmatisch met het document werken.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 3: Configureer lettertype-instellingen

 Maak een nieuwe`FontSettings` object en laad de fallback-instellingen voor lettertypen vanuit een XML-bestand. Dit XML-bestand bevat de regels voor het terugvallen van lettertypen.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Stap 4: Pas lettertype-instellingen toe op het document

 Wijs de geconfigureerde toe`FontSettings` naar het document. Dit zorgt ervoor dat de fallback-regels voor lettertypen worden toegepast bij het renderen van het document.

```csharp
doc.FontSettings = fontSettings;
```

## Stap 5: Sla het document op

Sla ten slotte het document op. De fallback-instellingen voor het lettertype worden tijdens de opslagbewerking gebruikt om een juiste lettertypevervanging te garanderen.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## XML-bestand: Fallback-regels voor lettertypen

Hier is een voorbeeld van hoe uw XML-bestand waarin de fallback-regels voor lettertypen worden gedefinieerd, eruit zou moeten zien:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Conclusie

Door deze stappen te volgen, kunt u Font Fallback-instellingen effectief instellen en gebruiken in Aspose.Words voor .NET. Dit zorgt ervoor dat uw documenten alle tekens correct weergeven, zelfs als het originele lettertype bepaalde tekens niet ondersteunt. Het implementeren van deze instellingen zal de kwaliteit en leesbaarheid van uw documenten aanzienlijk verbeteren.

## Veelgestelde vragen

### Vraag 1: Wat is lettertype-fallback?

Font Fallback is een functie waarmee lettertypen kunnen worden vervangen wanneer het originele lettertype bepaalde tekens niet ondersteunt, waardoor een juiste weergave van alle tekstelementen wordt gegarandeerd.

### V2: Kan ik meerdere reservelettertypen opgeven?

Ja, u kunt meerdere reservelettertypen opgeven in de XML-regels. Aspose.Words controleert elk lettertype in de aangegeven volgorde totdat er een wordt gevonden die het teken ondersteunt.

### V3: Waar kan ik Aspose.Words voor .NET downloaden?

 Je kunt het downloaden van de[Aspose-downloadpagina](https://releases.aspose.com/words/net/).

### V4: Hoe maak ik het XML-bestand voor de fallback-regels voor lettertypen?

Het XML-bestand kan met elke teksteditor worden gemaakt. Het moet de structuur volgen die wordt weergegeven in het voorbeeld in deze zelfstudie.

### V5: Is er ondersteuning beschikbaar voor Aspose.Words?

 Ja, u kunt ondersteuning vinden op de[Aspose.Words-ondersteuningsforum](https://forum.aspose.com/c/words/8).