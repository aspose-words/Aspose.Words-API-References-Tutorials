---
title: Zorg voor vervanging zonder achtervoegsels
linktitle: Zorg voor vervanging zonder achtervoegsels
second_title: Aspose.Words-API voor documentverwerking
description: In deze zelfstudie leert u hoe u achtervoegselloze overschrijvingen in een Word-document kunt krijgen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/get-substitution-without-suffixes/
---

In deze zelfstudie laten we u zien hoe u de overschrijvingen zonder achtervoegsels in een Word-document kunt krijgen met behulp van de Aspose.Words-bibliotheek voor .NET. Vervangingen zonder achtervoegsels worden gebruikt om problemen met lettertypevervanging op te lossen bij het weergeven of afdrukken van documenten. We nemen u stap voor stap mee om u te helpen de code in uw .NET-project te begrijpen en te implementeren.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd

## Stap 1: Definieer de documentmap
 Eerst moet u het mappad instellen op de locatie van uw Word-document. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad.

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het document en configureer vervangingen zonder achtervoegsels
 Vervolgens laden we het document met behulp van de`Document` klasse en configureer achtervoegselloze vervangingen met behulp van de`DocumentSubstitutionWarnings` klas. We zullen ook een lettertypebron toevoegen door een map op te geven die de lettertypen bevat.

```csharp
// Laad het document en configureer vervangingen zonder achtervoegsels
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Stap 3: Sla het document op
Ten slotte slaan we het document op met de toegepaste overschrijvingen zonder achtervoegsel.

```csharp
// Bewaar het document
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Voorbeeldbroncode voor Get Substitution Without Suffixes met Aspose.Words voor .NET 
```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Conclusie
In deze zelfstudie hebben we gezien hoe u de overschrijvingen zonder achtervoegsels in een Word-document kunt krijgen met Aspose.Words voor .NET. Vervangingen zonder achtervoegsels zijn handig voor het oplossen van problemen met het vervangen van lettertypen. U kunt deze functie gerust gebruiken om de weergave en het afdrukken van uw documenten te verbeteren.

### Veelgestelde vragen

#### Vraag: Waarom voegt Aspose.Words achtervoegsels toe aan lettertypevervangingen?

A: Aspose.Words voegt achtervoegsels toe aan lettertypevervangingen om conflicten tussen originele lettertypen en vervangende lettertypen te voorkomen. Dit zorgt voor maximale compatibiliteit bij het converteren en manipuleren van documenten.

#### Vraag: Hoe kan ik lettertypevervangingen zonder achtervoegsels ophalen in Aspose.Words?

 A: Om lettertypevervangingen zonder achtervoegsels in Aspose.Words op te halen, kunt u de`FontSubstitutionSettings` klasse en de`RemoveSuffixes` eigendom. Deze eigenschap instellen op`true` krijgt de lettertypevervangingen zonder de toegevoegde achtervoegsels.

#### Vraag: Is het mogelijk om het toevoegen van achtervoegsels aan lettertypevervangingen in Aspose.Words uit te schakelen?

A: Nee, het is niet mogelijk om het toevoegen van achtervoegsels aan lettertypevervangingen in Aspose.Words uit te schakelen. Er worden standaard achtervoegsels toegevoegd om de compatibiliteit en consistentie van documenten te garanderen.

#### Vraag: Hoe kan ik ongewenste achtervoegsels uit lettertypevervangingen in Aspose.Words filteren?

 A: Om ongewenste achtervoegsels uit lettertypevervangingen in Aspose.Words te filteren, kunt u tekenreeksverwerkingstechnieken gebruiken, zoals het gebruik van de`Replace` of`Substring` methoden om specifieke achtervoegsels te verwijderen die u niet wilt opnemen.