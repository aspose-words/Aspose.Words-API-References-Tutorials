---
title: Samenvoegveld invoegen met DOM
linktitle: Samenvoegveld invoegen met DOM
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u aangepaste samenvoegvelden voor velden invoegt in uw Word-documenten met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-merge-field-using-dom/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie "Insert Field Merge Field" van Aspose.Words voor .NET. Zorg ervoor dat u elke stap zorgvuldig volgt om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document en DocumentBuilder maken

We beginnen met het maken van een nieuw document en het initialiseren van een DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Cursor naar alinea verplaatsen

 Wij gebruiken de`MoveTo()` methode van de DocumentBuilder om de cursor naar de alinea te verplaatsen waar we het samenvoegveld willen invoegen.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Stap 4: Het samenvoegveld voor velden invoegen

 Wij gebruiken de DocumentBuilder`InsertField()` methode om een samenvoegveld voor velden in de alinea in te voegen.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Vervolgens configureren we de veldeigenschappen voor het samenvoegen van velden door de juiste opties op te geven, zoals de veldnaam, tekst voor en na het veld en verticale opmaakopties.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Tenslotte noemen wij de`Update()` methode om het veld bij te werken.

```csharp
field. Update();
```

### Voorbeeldbroncode voor het invoegen van een veldsamenvoegveld met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak het document en de DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Cursor naar alinea verplaatsen.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Veldsamenvoegveld invoegen.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Werk het veld bij.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

In dit voorbeeld hebben we een nieuw document gemaakt, de cursor naar de gewenste alinea verplaatst en vervolgens een samenvoegveld voor velden in het document ingevoegd.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een samenvoegveld invoegen in een Word-document met Aspose.Words voor .NET met de DOM?

A: Om een samenvoegveld in een Word-document in te voegen met Aspose.Words voor .NET met DOM, kunt u deze stappen volgen:

1. Navigeer naar de alinea waarin u het samenvoegveld wilt invoegen.
2.  Maak een`FieldMergeField` voorwerp.
3. Stel de eigenschappen van het samenvoegveld in, zoals de veldnaam en opmaakopties.
4.  Voeg het samenvoegveld toe aan de alinea met behulp van de`Paragraph.AppendChild` methode.

#### Vraag: Hoe kan ik brongegevens opgeven voor het samenvoegveld in Aspose.Words voor .NET?

A: Om de brongegevens voor het samenvoegveld in Aspose.Words voor .NET op te geven, kunt u de`FieldMergeField.FieldName` methode om de samenvoegveldnaam in te stellen, wat de naam is van een veld in een externe gegevensbron zoals een CSV-bestand, database, enz. U kunt ook de`FieldMergeField.Text` methode om de samenvoegveldwaarde rechtstreeks in te stellen.

#### Vraag: Kan ik de weergave van het samenvoegveld in een Word-document aanpassen met Aspose.Words voor .NET?

 A: Ja, u kunt het uiterlijk van het samenvoegveld in een Word-document aanpassen met Aspose.Words voor .NET. U kunt de opmaakopties instellen, zoals hoofdlettergebruik, lettertype, kleur, enz. met behulp van de eigenschappen van het`FieldMergeField` voorwerp.

#### Vraag: Hoe kan ik controleren of een samenvoegveld met succes is ingevoegd in een Word-document met Aspose.Words voor .NET?

 A: Om te controleren of een samenvoegveld succesvol is ingevoegd, kunt u door de documentinhoud bladeren en zoeken naar samenvoegveldexemplaren. U kunt de methoden en eigenschappen van de`Document` bezwaar maken tegen toegang tot paragrafen, velden en andere elementen van het document.

#### Vraag: Heeft het invoegen van een samenvoegveld met DOM invloed op de Word-documentstructuur met Aspose.Words voor .NET?

A: Het invoegen van een samenvoegveld met behulp van de DOM heeft geen directe invloed op de structuur van het Word-document. Het voegt echter een nieuw veldelement toe aan de documentinhoud. U kunt de documentstructuur manipuleren door de bestaande elementen toe te voegen, te verwijderen of te wijzigen, afhankelijk van uw behoeften.