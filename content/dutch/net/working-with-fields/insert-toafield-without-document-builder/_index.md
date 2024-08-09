---
title: TOA-veld invoegen zonder Document Builder
linktitle: TOA-veld invoegen zonder Document Builder
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een TOA-veld invoegt zonder een documentbuilder te gebruiken in Aspose.Words voor .NET. Volg onze stapsgewijze handleiding om juridische citaten efficiënt te beheren.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-toafield-without-document-builder/
---
## Invoering

Het maken van een TOA-veld (Tabel met autoriteiten) in een Word-document kan aanvoelen als het samenstellen van een complexe puzzel. Met de hulp van Aspose.Words voor .NET wordt het proces echter soepel en eenvoudig. In dit artikel begeleiden we u bij de stappen om een TOA-veld in te voegen zonder gebruik te maken van een documentbuilder, waardoor u gemakkelijk uw citaten en juridische verwijzingen in uw Word-documenten kunt beheren.

## Vereisten

Voordat we in de tutorial duiken, laten we eerst de essentiële zaken bespreken die je nodig hebt:

-  Aspose.Words voor .NET: Zorg ervoor dat de nieuwste versie is geïnstalleerd. Je kunt het downloaden van de[Aspose-website](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: een .NET-compatibele IDE zoals Visual Studio.
- Basiskennis van C#: Het begrijpen van de basissyntaxis en concepten van C# zal nuttig zijn.
- Voorbeeld van een Word-document: Maak een voorbeelddocument of zorg dat u het bij de hand heeft waarin u het TOA-veld wilt invoegen.

## Naamruimten importeren

Om aan de slag te gaan, moet u de benodigde naamruimten uit de Aspose.Words-bibliotheek importeren. Deze opstelling zorgt ervoor dat u toegang heeft tot alle klassen en methoden die nodig zijn voor documentmanipulatie.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Laten we het proces opsplitsen in eenvoudige, gemakkelijk te volgen stappen. We begeleiden u bij elke fase en leggen uit wat elk stukje code doet en hoe het bijdraagt aan het creëren van het TOA-veld.

## Stap 1: Initialiseer het document

 Eerst moet u een exemplaar maken van de`Document` klas. Dit object vertegenwoordigt het Word-document waaraan u werkt.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

Deze code initialiseert een nieuw Word-document. U kunt het zien als het creëren van een leeg canvas waaraan u uw inhoud toevoegt.

## Stap 2: Maak en configureer het TA-veld

Vervolgens voegen we een TA-veld (Table of Authorities) toe. Dit veld markeert de vermeldingen die in de TOA zullen verschijnen.

```csharp
Paragraph para = new Paragraph(doc);

// We willen TA- en TOA-velden als volgt invoegen:
// { TA \c 1 \l "Waarde 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

Hier is een overzicht:
- Paragraaf para = new Paragraph(doc);: Creëert een nieuwe paragraaf binnen het document.
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);: Voegt een TA-veld toe aan de alinea. De`FieldType.FieldTOAEntry` geeft aan dat dit een TOA-invoerveld is.
- fieldTA.EntryCategory = "1";: Stelt de itemcategorie in. Dit is handig voor het categoriseren van verschillende soorten vermeldingen.
- fieldTA.LongCitation = "Waarde 0";: Specificeert de lange citatietekst. Dit is de tekst die in de TOA zal verschijnen.
- doc.FirstSection.Body.AppendChild(para);: Voegt de alinea met het TA-veld toe aan de hoofdtekst van het document.

## Stap 3: Voeg het TOA-veld toe

Nu voegen we het daadwerkelijke TOA-veld in dat alle TA-gegevens in een tabel verzamelt.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

In deze stap:
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);: Voegt een TOA-veld toe aan de alinea.
- fieldToa.EntryCategory = "1";: Filtert de vermeldingen zodat deze alleen de vermeldingen bevat die zijn gemarkeerd met categorie "1".

## Stap 4: Werk het TOA-veld bij

Nadat u het TOA-veld heeft ingevoegd, moet u het bijwerken om er zeker van te zijn dat het de nieuwste vermeldingen weerspiegelt.

```csharp
fieldToa.Update();
```

Deze opdracht vernieuwt het TOA-veld en zorgt ervoor dat alle gemarkeerde vermeldingen correct in de tabel worden weergegeven.

## Stap 5: Bewaar het document

Sla ten slotte uw document op met het nieuw toegevoegde TOA-veld.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 Met deze coderegel wordt het document in de opgegeven map opgeslagen. Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar u uw bestand wilt opslaan.

## Conclusie

En daar heb je het! U hebt met succes een TOA-veld aan een Word-document toegevoegd zonder gebruik te maken van een documentbuilder. Door deze stappen te volgen, kunt u citaten efficiënt beheren en uitgebreide tabellen met autoriteiten in uw juridische documenten maken. Aspose.Words voor .NET maakt dit proces soepel en efficiënt, waardoor u de tools krijgt om complexe documenttaken met gemak uit te voeren.

## Veelgestelde vragen

### Kan ik meerdere TA-velden met verschillende categorieën toevoegen?
 Ja, u kunt meerdere TA-velden met verschillende categorieën toevoegen door de`EntryCategory`eigendom dienovereenkomstig.

### Hoe kan ik het uiterlijk van de TOA aanpassen?
U kunt het uiterlijk van de TOA aanpassen door de eigenschappen van het TOA-veld te wijzigen, zoals de invoeropmaak en categorielabels.

### Is het mogelijk om het TOA-veld automatisch bij te werken?
 Hoewel u het TOA-veld handmatig kunt bijwerken met behulp van de`Update` methode ondersteunt Aspose.Words momenteel geen automatische updates van documentwijzigingen.

### Kan ik TA-velden programmatisch toevoegen aan specifieke delen van het document?
Ja, u kunt op specifieke locaties TA-velden toevoegen door deze in de gewenste paragrafen of secties in te voegen.

### Hoe ga ik om met meerdere TOA-velden in één document?
 U kunt meerdere TOA-velden beheren door er verschillende toe te wijzen`EntryCategory` waarden en ervoor te zorgen dat elk TOA-veld vermeldingen filtert op basis van zijn categorie.