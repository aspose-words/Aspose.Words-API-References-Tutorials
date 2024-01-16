---
title: Voeg ASKField in zonder Document Builder
linktitle: Voeg ASKField in zonder Document Builder
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een ASK-veld in uw Word-documenten invoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie "Een ASK-veld invoegen zonder DocumentBuilder" van Aspose.Words voor .NET. Zorg ervoor dat u elke stap zorgvuldig volgt om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document en de alinea maken

We beginnen met het maken van een nieuw document en het ophalen van de eerste alinea.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Stap 3: Het ASK-veld invoegen

 Wij gebruiken de`AppendField()` methode om een ASK-veld in de alinea in te voegen.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Vervolgens configureren we de verschillende eigenschappen van het ASK-veld door de gewenste waarden op te geven.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Tenslotte noemen wij de`Update()` methode om het veld bij te werken.

```csharp
field. Update();
```

### Voorbeeld van de broncode voor het invoegen van een ASK-veld zonder DocumentBuilder met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Documentcreatie.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Voeg het VRAAG-veld in.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

In dit voorbeeld hebben we een nieuw document gemaakt, een ASK-veld ingevoegd zonder DocumentBuilder te gebruiken, de verschillende eigenschappen van het veld geconfigureerd en het document opgeslagen met een opgegeven bestandsnaam.

Dit is het einde van onze handleiding over het gebruik van de functie "Vraagveld invoegen zonder DocumentBuilder" met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Wat is een ASK-veld in Aspose.Words?

A: Een ASK-veld in Aspose.Words wordt gebruikt om de gebruiker een vraag te stellen bij het openen van een document. Het wordt vaak gebruikt om specifieke informatie of feedback op te vragen, die van gebruiker tot gebruiker kan verschillen.

#### Vraag: Hoe kan ik het ASK-veld in een Word-document invoegen zonder Document Builder in Aspose.Words te gebruiken?

A: Om een ASK-veld in een Word-document in te voegen zonder Document Builder in Aspose.Words te gebruiken, kunt u deze stappen volgen:

1. Importeer de document- en veldklasse uit de Aspose.Words.Fields-naamruimte.
2. Maak een exemplaar van Document door uw bestaande document te laden.
3. Gebruik de InsertField-methode om een ASK-veld in te voegen door de vraagnaam op te geven.
4. Bewaar het document.

#### Vraag: Hoe krijg ik de gebruikersreactie voor een ASK-veld in een Word-document?

A: Om het antwoord van de gebruiker op een ASK-veld in een Word-document te krijgen, kunt u de GetFieldNames-methode gebruiken die beschikbaar is in de Document-klasse. Deze methode retourneert een lijst met de namen van de velden in het document. Vervolgens kunt u controleren of de ASK-veldnaam in de lijst aanwezig is en het bijbehorende antwoord ophalen.

#### Vraag: Kan het ASK-veld worden gebruikt om meer informatie van de gebruiker op te vragen?

A: Ja, het VRAAG-veld kan worden gebruikt om meerdere gegevens van de gebruiker op te vragen. U kunt meerdere ASK-velden in uw document invoegen, elk met een andere vraag. Wanneer het document wordt geopend, wordt de gebruiker om de bijbehorende antwoorden gevraagd.