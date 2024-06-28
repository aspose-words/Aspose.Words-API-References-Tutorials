---
title: Stel de MS Word-versie in
linktitle: Stel de MS Word-versie in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document laadt met een opgegeven versie van MS Word met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-loadoptions/set-ms-word-version/
---
Bij het verwerken van Word-documenten in een C#-toepassing kan het nodig zijn om de versie van Microsoft Word op te geven die moet worden gebruikt bij het laden van het document. Met de Aspose.Words-bibliotheek voor .NET kunt u eenvoudig instellen welke versie van MS Word u wilt gebruiken met behulp van LoadOptions. In deze stapsgewijze handleiding laten we u zien hoe u Aspose.Words voor .NET C#-broncode kunt gebruiken om een document te laden met een opgegeven versie van MS Word met behulp van de laadopties van LoadOptions.

## Inzicht in de Aspose.Words-bibliotheek

Voordat u in de code duikt, is het belangrijk dat u de Aspose.Words-bibliotheek voor .NET begrijpt. Aspose.Words is een krachtige bibliotheek voor het maken, bewerken, converteren en beschermen van Word-documenten op verschillende platforms, waaronder .NET. Het biedt veel functies voor het manipuleren van documenten, zoals het invoegen van tekst, het wijzigen van de opmaak, het toevoegen van secties en nog veel meer.

## Laadopties configureren

De eerste stap is het configureren van de laadopties voor ons document. Gebruik de klasse LoadOptions om laadparameters op te geven. In ons geval moeten we de eigenschap MswVersion instellen op de gewenste versie van MS Word. We gebruiken bijvoorbeeld de Microsoft Word 2010-versie. Hier ziet u hoe u het moet doen:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

We maken een nieuw LoadOptions-object en stellen de eigenschap MswVersion in op MsWordVersion.Word2010 om de versie van MS Word 2010 op te geven.

## Documenten laden met de opgegeven versie van MS Word

Nu we de laadopties hebben geconfigureerd, kunnen we het document laden met behulp van de Document-klasse en de laadopties specificeren. Hier is een voorbeeld :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

In dit voorbeeld laden we het document "Document.docx" in de documentenmap met behulp van de opgegeven laadopties.

### Voorbeeldbroncode voor LoadOptions met de functionaliteit "MS Word-versie instellen" met behulp van Aspose.Words voor .NET

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configureer laadopties met de functie "MS Word-versie instellen".
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Laad het document met de opgegeven versie van MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Bewaar het document
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Conclusie

In deze handleiding hebben we uitgelegd hoe u een document kunt uploaden waarin een specifieke versie van MS Word wordt gespecificeerd met behulp van de Aspose.Words-bibliotheek voor .NET. Door de gegeven stappen te volgen en de meegeleverde code C#-bron te gebruiken, kunt u deze functionaliteit eenvoudig toepassen in uw C#-applicatie. Door een document met een gespecificeerde versie van MS Word te laden, kunt u een goede compatibiliteit en verwerking van het document in uw applicatie garanderen.


### Veelgestelde vragen

#### Vraag: Waarom moet ik de versie van MS Word opgeven bij het laden van een document in een C#-toepassing?

Het opgeven van de versie van MS Word zorgt ervoor dat het document correct wordt geladen en verwerkt, vooral als het gaat om specifieke opmaak of functies die kunnen variëren tussen verschillende versies.

#### Vraag: Welke versies van MS Word ondersteunt Aspose.Words?

A: Aspose.Words voor .NET ondersteunt verschillende versies van MS Word, waaronder Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 en meer.

#### Vraag: Kan ik een document laden met een andere versie van MS Word dan de versie die op mijn systeem is geïnstalleerd?

A: Ja, met Aspose.Words kunt u een andere versie van MS Word opgeven bij het laden van het document, waardoor compatibiliteit wordt gegarandeerd, zelfs als het doelsysteem een andere MS Word-versie heeft.

#### Vraag: Welke voordelen heeft het instellen van de MS Word-versie voor mijn C#-applicatie?

A: Door de MS Word-versie in te stellen, zorgt u ervoor dat het document wordt verwerkt volgens de beoogde opmaak en functies van die specifieke versie, waardoor consistente uitvoer wordt verkregen.

#### Vraag: Is Aspose.Words beperkt tot het verwerken van alleen DOCX-documenten?

A: Nee, Aspose.Words ondersteunt verschillende documentformaten, waaronder DOC, RTF, HTML, PDF en meer, waardoor het een veelzijdige tool is voor het verwerken van verschillende soorten documenten.