---
title: Stel de map TrueType-lettertypen in
linktitle: Stel de map TrueType-lettertypen in
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van de map True Type Fonts bij het renderen van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/set-true-type-fonts-folder/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om de map True Type Fonts in te stellen bij het renderen van een document met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u een aangepaste map met True Type-lettertypen kunt opgeven die u kunt gebruiken bij het renderen van uw documenten met Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar u uw bewerkte, gerenderde document wilt opslaan. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het document dat u wilt renderen
 Vervolgens moet u het document laden om te renderen met behulp van de`Document` klas. Zorg ervoor dat u het juiste documentpad opgeeft.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 3: Stel de map TrueType-lettertypen in
Nu kunt u de map met True Type-lettertypen opgeven die u wilt gebruiken bij het renderen, door een exemplaar van het`FontSettings` klasse en het gebruik van de`SetFontsFolder()` methode om de map met lettertypen in te stellen. U kunt een aangepaste map opgeven met uw TrueType-lettertypen. De tweede parameter voor`SetFontsFolder()` geeft aan of u ook in submappen van de opgegeven map wilt zoeken.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Stap 4: Sla het gerenderde document op
 Ten slotte kunt u het gerenderde document opslaan in een bestand met behulp van de`Save()` werkwijze van de`Document` klas. Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Voorbeeldbroncode voor Set True Type Fonts Folder met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Houd er rekening mee dat deze instelling alle standaardlettertypebronnen overschrijft die standaard worden doorzocht. Nu wordt alleen naar deze mappen gezocht
// Lettertypen bij het renderen of insluiten van lettertypen. Als u een extra lettertypebron wilt toevoegen terwijl u de systeemlettertypebronnen behoudt, gebruikt u zowel FontSettings.GetFontSources als
// FontSettings.SetFontSources in plaats daarvan
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Lettertype-instellingen instellen
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de map True Type Fonts kunt instellen bij het renderen van een document met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig een aangepaste map opgeven met True Type-lettertypen die u kunt gebruiken bij het renderen van uw documenten. Aspose.Words biedt een krachtige en flexibele API voor woordenverwerking met lettertypen in uw documenten. Met deze kennis kunt u de gebruikte lettertypen bij het renderen van uw documenten beheren en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Hoe kan ik de map TrueType-lettertypen in Aspose.Words configureren?

 A: Om de map TrueType-lettertypen in Aspose.Words te configureren, kunt u de`SetTrueTypeFontsFolder` werkwijze van de`Fonts` klasse die de locatie specificeert van de map die de TrueType-lettertypen bevat.

#### Vraag: Welke typen lettertypen worden beschouwd als TrueType-lettertypen?

A: TrueType-lettertypen zijn een populair lettertypeformaat. Ze worden vaak gebruikt in Word-documenten en hebben de bestandsextensie .ttf of .ttc.

#### Vraag: Kan ik meerdere TrueType-lettertypemappen opgeven in Aspose.Words?

A: Ja, u kunt meerdere TrueType-lettertypemappen opgeven in Aspose.Words met behulp van de`SetTrueTypeFontsFolder` werkwijze van de`Fonts` klasse met een lijst met maplocaties.

#### Vraag: Hoe kan ik de TrueType-lettertypenmap controleren die is geconfigureerd in Aspose.Words?

 A: Om de geconfigureerde map TrueType Fonts in Aspose.Words te controleren, kunt u de`GetTrueTypeFontsFolder` werkwijze van de`Fonts` class om de locatie van de geconfigureerde map TrueType Fonts op te halen.

#### Vraag: Waarom is het belangrijk om de map TrueType-lettertypen in Aspose.Words te configureren?

A: Het instellen van de map TrueType-lettertypen in Aspose.Words is belangrijk omdat Aspose.Words hiermee de lettertypen kan vinden die nodig zijn bij het verwerken van Word-documenten. Dit zorgt voor consistentie in documentopmaak en -uiterlijk, zelfs op verschillende systemen.