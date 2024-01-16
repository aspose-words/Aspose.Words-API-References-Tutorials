---
title: Voeg Bidi-markeringen toe aan een Word-document
linktitle: Voeg Bidi-markeringen toe aan een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Bidi-markeringen kunt toevoegen aan een Word-document met behulp van Aspose.Words voor .NET en professionele meertalige documenten kunt maken.
type: docs
weight: 10
url: /nl/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words voor .NET is een krachtige bibliotheek voor het maken, bewerken en manipuleren van Word-documenten in een C#-toepassing. Een van de functies van Aspose.Words is de mogelijkheid om Bidi-markeringen (bidirectioneel) aan een document toe te voegen. In deze handleiding laten we u zien hoe u de C#-broncode van Aspose.Words voor .NET kunt gebruiken om Bidi-markeringen aan een document toe te voegen.

## Inzicht in de Aspose.Words-bibliotheek

Voordat u in de code duikt, is het belangrijk dat u de Aspose.Words-bibliotheek voor .NET begrijpt. Aspose.Words is een populaire bibliotheek die het verwerken van woorden met Word-documenten eenvoudig en efficiënt maakt. Het biedt een breed scala aan functies voor het maken, bewerken en manipuleren van Word-documenten, inclusief het toevoegen van Bidi-markeringen.

## Het document maken en inhoud toevoegen

De eerste stap is het maken van een nieuw document en het toevoegen van inhoud eraan. Gebruik de klasse Document om een nieuw documentexemplaar te maken. Gebruik vervolgens de klasse DocumentBuilder om tekst aan het document toe te voegen. Hier is een voorbeeld :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

In dit voorbeeld maken we een nieuw document en gebruiken we de DocumentBuilder om tekst toe te voegen. We hebben drie regels tekst toegevoegd: één in het Engels, één in het Hebreeuws en één in het Arabisch om aan te tonen dat u inhoud in verschillende talen toevoegt.

## Bidi-markeringen toegevoegd

Nadat de inhoud is toegevoegd, kunnen we nu Bidi-markeringen aan het document toevoegen. Hiervoor gebruiken we de klasse TxtSaveOptions en stellen we de eigenschap AddBidiMarks in op true. Hier is hoe:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

In dit voorbeeld maken we een exemplaar van TxtSaveOptions en stellen we de eigenschap AddBidiMarks in op true. Vervolgens gebruiken we de Save-methode van de Document-klasse om het document met Bidi-markeringen op te slaan.

### Voorbeeldbroncode voor de functionaliteit "Bidi-markeringen toevoegen" met Aspose.Words voor .NET

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak het document en voeg inhoud toe
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Voeg Bidi-markeringen toe
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Conclusie

In deze handleiding hebben we uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om Bidi-markeringen toe te voegen aan een Word-document met behulp van de meegeleverde C#-broncode. Door de aangegeven stappen te volgen, kunt u eenvoudig Bidi-markeringen toevoegen aan uw Word-documenten in uw C#-applicatie. Aspose.Words biedt enorme flexibiliteit en kracht voor woordenverwerking met tekstopmaak en taalbeheer, waardoor u op professionele wijze meertalige documenten kunt maken.

### Veel Gestelde Vragen

#### Vraag: Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor het maken, bewerken en manipuleren van Word-documenten in een C#-toepassing. Het biedt veel functies voor woordenverwerking met Word-documenten, waaronder het toevoegen van Bidi-markeringen (bidirectioneel).

#### Vraag: Welke functies biedt Aspose.Words voor .NET?
Aspose.Words voor .NET biedt een breed scala aan functies voor het maken, bewerken en manipuleren van Word-documenten. Enkele van deze functies zijn onder meer het maken van documenten, het toevoegen van inhoud, het opmaken van tekst, het beheren van tabellen, het samenvoegen en splitsen van documenten, het converteren van documenten en meer.

#### Vraag: Hoe kan ik Bidi-markeringen toevoegen aan een Word-document met Aspose.Words voor .NET?
U kunt Bidi-markeringen toevoegen aan een Word-document door deze stappen te volgen:

 Maak een nieuw document met behulp van de`Document` klas.

 Gebruik de`DocumentBuilder` klasse om inhoud aan het document toe te voegen.

 Nadat u de inhoud heeft toegevoegd, gebruikt u de`TxtSaveOptions` klasse en stel de`AddBidiMarks`eigendom aan`true`.

 Sla het document met Bidi-markeringen op met behulp van de`Save` werkwijze van de`Document` klas.

#### Vraag: Ondersteunt Aspose.Words meerdere talen voor het toevoegen van Bidi-markeringen?
Ja, Aspose.Words ondersteunt meerdere talen voor het toevoegen van Bidi-markeringen. U kunt Bidi-markeringen toevoegen aan tekst in verschillende talen, zoals Engels, Hebreeuws en Arabisch, met behulp van Aspose.Words voor .NET.

#### Vraag: Zijn er extra opties om het document met Bidi-markeringen op te slaan?
 Ja, u kunt andere opties opgeven wanneer u het document met Bidi-markeringen opslaat met behulp van de`TxtSaveOptions` klas. U kunt bijvoorbeeld het documentopslagformaat, de coderingsopties, enz. instellen.