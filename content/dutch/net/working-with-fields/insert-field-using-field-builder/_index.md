---
title: Veld invoegen met Field Builder
linktitle: Veld invoegen met Field Builder
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u aangepaste velden in uw Word-documenten kunt invoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-field-using-field-builder/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie "Een veld invoegen met FieldBuilder" van Aspose.Words voor .NET. Zorg ervoor dat u elke stap zorgvuldig volgt om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document aanmaken

We beginnen met het maken van een nieuw document.

```csharp
Document doc = new Document();
```

## Stap 3: Bouw het IF-veld met FieldBuilder

We gebruiken de klasse FieldBuilder om een IF-veld te construeren met twee geneste MERGEFIELD-velden. In dit voorbeeld worden in het IF-veld de voor- en achternaam weergegeven op basis van een voorwaarde.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Stap 4: Het IF-veld in het document invoegen

 Wij gebruiken de`BuildAndInsert()` methode om het IF-veld op een specifieke locatie in het document te bouwen en in te voegen.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Voorbeeldbroncode voor het invoegen van een veld met FieldBuilder met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Documentcreatie.
Document doc = new Document();

// Constructie van het IF-veld met FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Voeg het IF-veld in het document in.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

In dit voorbeeld hebben we een nieuw document gemaakt, een IF-veld met geneste MERGEFIELD-velden gemaakt en dat veld vervolgens op een opgegeven locatie in het document ingevoegd. Het document wordt vervolgens opgeslagen met een specifieke bestandsnaam.

### Veelgestelde vragen

#### Vraag: Wat is een veldconstructor in Aspose.Words?

A: Een Field Builder in Aspose.Words is een krachtig hulpmiddel voor het maken en manipuleren van velden in een Word-document. Het biedt geavanceerde functies voor het bouwen en aanpassen van velden, inclusief het invoegen van veldcodes en het beheren van opmaakopties.

#### Vraag: Welke typen velden kunnen worden ingevoegd met de veldbouwer?

A: Met de veldbouwer in Aspose.Words kunt u verschillende soorten velden in een Word-document invoegen. Hier volgen enkele voorbeelden van veelgebruikte veldtypen:

- MERGEFIELD: gebruikt om gegevens uit externe bronnen samen te voegen.
- DATUM: toont de huidige datum.
- PAGINA: toont het huidige paginanummer.
- IF: maakt het mogelijk om de weergave van een inhoud te conditioneren volgens een voorwaarde.
- TOC: genereert automatisch een inhoudsopgave op basis van de documenttitelstijlen.

#### Vraag: Hoe kan ik de velden aanpassen die zijn ingevoegd met de veldbouwer?

A: De veldbouwer biedt aanpassingsopties voor ingevoegde velden. U kunt veldconstructormethoden en -eigenschappen gebruiken om opties in te stellen, zoals veldopmaak, argumenten, schakelopties en standaardwaarden. U kunt bijvoorbeeld het datumformaat, het getalformaat, het scheidingsteken voor duizendtallen, enz. instellen.
  