---
title: Voeg ASKField in zonder Document Builder
linktitle: Voeg ASKField in zonder Document Builder
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een ASK-veld invoegt zonder Document Builder te gebruiken in Aspose.Words voor .NET. Volg deze handleiding om uw Word-documenten dynamisch te verbeteren.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-askfield-with-out-document-builder/
---
## Invoering

Wilt u documentautomatisering onder de knie krijgen met Aspose.Words voor .NET? U bent bij ons aan het juiste adres! Vandaag laten we u zien hoe u een ASK-veld kunt invoegen zonder een Document Builder te gebruiken. Dit is een handige functie als u wilt dat uw document gebruikers om specifieke invoer vraagt, waardoor uw Word-documenten interactiever en dynamischer worden. Dus laten we erin duiken en uw documenten slimmer maken!

## Vereisten

Voordat we onze handen vuil maken met wat code, moeten we ervoor zorgen dat we alles hebben ingesteld:

1.  Aspose.Words voor .NET: Zorg ervoor dat deze bibliotheek is geïnstalleerd. Als dit niet het geval is, kunt u deze downloaden van[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Een geschikte IDE zoals Visual Studio.
3. .NET Framework: Zorg ervoor dat .NET Framework is geïnstalleerd.

Geweldig! Nu we helemaal klaar zijn, gaan we beginnen met het importeren van de benodigde naamruimten.

## Naamruimten importeren

Allereerst moeten we de naamruimte Aspose.Words importeren om toegang te krijgen tot alle functies van Aspose.Words voor .NET. Zo doe je het:

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

## Stap 1: Maak een nieuw document

Voordat we een ASK-veld kunnen invoegen, hebben we een document nodig om mee te werken. Zo maakt u een nieuw document:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Documentcreatie.
Document doc = new Document();
```

Met dit codefragment wordt een nieuw Word-document ingesteld waarin we ons ASK-veld toevoegen.

## Stap 2: Ga naar het alineaknooppunt

In een Word-document is de inhoud georganiseerd in knooppunten. We moeten toegang krijgen tot het eerste alineaknooppunt waar we ons ASK-veld zullen invoegen:

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

Met deze coderegel wordt de eerste alinea in het document opgehaald, klaar voor het invoegen van ons ASK-veld.

## Stap 3: Voeg het ASK-veld in

Laten we nu naar de hoofdgebeurtenis gaan: het invoegen van het ASK-veld. Dit veld zal de gebruiker om invoer vragen wanneer het document wordt geopend.

```csharp
// Voeg het VRAAG-veld in.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Hier voegen we een ASK-veld toe aan de alinea. Simpel, toch?

## Stap 4: Configureer het ASK-veld

We moeten enkele eigenschappen instellen om te definiëren hoe het ASK-veld zich gedraagt. Laten we de bladwijzernaam, prompttekst, standaardantwoord en samenvoeggedrag configureren:

```csharp
field.BookmarkName = "Test1";
field.PromptText = "Please enter your response:";
field.DefaultResponse = "Default response";
field.PromptOnceOnMailMerge = true;
```

- BookmarkName: Een unieke identificatie voor het ASK-veld.
- PromptText: de tekst die de gebruiker om invoer vraagt.
- DefaultResponse: Het vooraf ingevulde antwoord dat de gebruiker kan wijzigen.
- PromptOnceOnMailMerge: Bepaalt of de prompt slechts één keer verschijnt tijdens een samenvoegbewerking.

## Stap 5: Werk het veld bij

Nadat we het ASK-veld hebben geconfigureerd, moeten we het bijwerken om ervoor te zorgen dat alle instellingen correct worden toegepast:

```csharp
field.Update();
```

Deze opdracht zorgt ervoor dat ons ASK-veld gereed is en correct is ingesteld in het document.

## Stap 6: Sla het document op

Laten we ten slotte het document opslaan in de door u opgegeven map:

```csharp
doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Deze regel slaat het document op met het ingevoegde ASK-veld. En daar heb je het: je document is nu uitgerust met een dynamisch ASK-veld!

## Conclusie

Gefeliciteerd! U hebt zojuist een ASK-veld aan een Word-document toegevoegd met Aspose.Words voor .NET zonder de Document Builder. Deze functie kan de gebruikersinteractie met uw documenten aanzienlijk verbeteren, waardoor ze flexibeler en gebruiksvriendelijker worden. Blijf experimenteren met verschillende velden en eigenschappen om het volledige potentieel van Aspose.Words te ontsluiten. Veel codeerplezier!

## Veelgestelde vragen

### Wat is een ASK-veld in Aspose.Words?
Een ASK-veld in Aspose.Words is een veld dat de gebruiker om specifieke invoer vraagt wanneer het document wordt geopend, waardoor dynamische gegevensinvoer mogelijk is.

### Kan ik meerdere ASK-velden in één document gebruiken?
Ja, u kunt meerdere ASK-velden in een document invoegen, elk met unieke aanwijzingen en antwoorden.

###  Wat is het doel van de`PromptOnceOnMailMerge` property?
 De`PromptOnceOnMailMerge` eigenschap bepaalt of de ASK-prompt slechts één keer verschijnt tijdens een samenvoegbewerking of elke keer.

### Moet ik het ASK-veld bijwerken nadat ik de eigenschappen ervan heb ingesteld?
Ja, het bijwerken van het ASK-veld zorgt ervoor dat alle eigenschappen correct worden toegepast en dat het veld naar verwachting functioneert.

### Kan ik de prompttekst en het standaardantwoord aanpassen?
Absoluut! U kunt aangepaste prompttekst en standaardantwoorden instellen om het VRAAG-veld aan uw specifieke behoeften aan te passen.