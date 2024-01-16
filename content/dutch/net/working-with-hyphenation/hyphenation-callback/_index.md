---
title: Terugbellen bij woordafbreking
linktitle: Terugbellen bij woordafbreking
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u callback voor woordafbreking kunt gebruiken in Aspose.Words voor .NET om woordafbreking af te handelen.
type: docs
weight: 10
url: /nl/net/working-with-hyphenation/hyphenation-callback/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u de functie voor het terugbellen van woordafbreking in Aspose.Words voor .NET gebruikt. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Zorg er om te beginnen voor dat Aspose.Words voor .NET is geïnstalleerd en geconfigureerd in uw ontwikkelomgeving. Als u dat nog niet heeft gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Afbreekherinnering opslaan

 Eerst registreren we de terugbelafbreking met behulp van een custom`CustomHyphenationCallback` klas. Hierdoor kunnen we woordafbreking volgens onze eigen regels afhandelen:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Zorg ervoor dat u de`CustomHyphenationCallback` klasse volgens uw specifieke behoeften.

## Stap 2: Het document laden en woordafbreking toepassen

Laad vervolgens uw document vanuit de opgegeven map en koppel de woorden af met Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Stap 3: Ontbrekende woordenboekfouten verwerken

Als er een woordafbrekingswoordenboek ontbreekt, vangen we de overeenkomstige uitzondering op en geven we een foutmelding weer:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Stap 4: Herinnering voor woordafbreking opruimen en uitschakelen

Voer ten slotte de volgende stappen uit voor netheid en om de herinnering voor woordafbreking uit te schakelen:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Hiermee wordt de herinnering voor woordafbreking opgeschoond en uitgeschakeld nadat de verwerking is voltooid.

Dus ! U hebt met succes callback voor afbreking gebruikt in Aspose.Words voor .NET.

### Voorbeeldbroncode voor terugbellen bij woordafbreking met Aspose.Words voor .NET

```csharp
try
{
	 // Registreer terugbelafbreking.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Wat is een syllabisatieherinnering in Aspose.Words?

A: Een Syllabisatieherinnering in Aspose.Words is een functie waarmee u kunt aanpassen hoe woorden in uw documenten worden gesyllabiseerd. Door een syllabiseringsherinnering te gebruiken, kunt u aangepaste regels opgeven voor de syllabisering van woorden, wat handig kan zijn voor specifieke talen of bepaalde scenario's waarin de standaard syllabisering niet de gewenste resultaten oplevert.

#### Vraag: Hoe stel ik een syllabisatieherinnering in Aspose.Words in?

 A: Om een callback voor woordafbreking in Aspose.Words te definiëren, moet u een klasse maken die de`HyphenationCallback` interface en implementeer de`HandleWord()` methode. Deze methode wordt aangeroepen voor elk woord dat je tijdens de syllabisering tegenkomt. U kunt er aangepaste syllabiseringsregels op toepassen en het syllabiseerde woord retourneren. Vervolgens kunt u uw terugroepafbreking binden met behulp van de`Document.HyphenationCallback` eigendom van uw document.

#### Vraag: Wat is het voordeel van het gebruik van een syllabisatieherinnering in Aspose.Words?

A: Het voordeel van het gebruik van een syllabisatieherinnering in Aspose.Words is de mogelijkheid om aan te passen hoe woorden in uw documenten in syllabisatie worden weergegeven. Dit geeft u meer controle over de syllabisatie, vooral voor specifieke talen of scenario's waarin de standaard syllabisatie niet de gewenste resultaten oplevert. U kunt specifieke regels op elk woord toepassen om een nauwkeurige syllabisatie te verkrijgen die aansluit bij uw behoeften.

#### Vraag: Wat zijn enkele veel voorkomende scenario's waarbij het gebruik van een syllabiseringsherinnering nuttig kan zijn?

A: Het gebruik van een syllabiseringsbooster kan in verschillende scenario's nuttig zijn, zoals:
- Syllabisatie van woorden in specifieke talen die bepaalde syllabisatieregels hebben.
- De toepassing van gepersonaliseerde syllabisatieregels voor acroniemen of technische woorden.
- Aanpassing van syllabisatie volgens stilistische voorkeuren of typografische normen.

#### Vraag: Hoe kan ik aangepaste syllabisatie testen met een syllabisatieherinnering in Aspose.Words?

 A: Om aangepaste syllabisatie te testen met een syllabisatieherinnering in Aspose.Words, kunt u een testdocument maken met woorden waarop u aangepaste syllabisatieregels wilt toepassen. Vervolgens kunt u uw aangepaste syllabisatie-callback instellen, bel de`Document.Range.Replace()` methode om de woorden in het document te vervangen, en gebruik de`Hyphenate()` werkwijze van de`Hyphenation` klasse om de syllabisatie van de woorden te krijgen. Vervolgens kunt u de syllabische woorden naar wens opmaken, bijvoorbeeld door koppeltekens tussen lettergrepen toe te voegen.