---
title: Hernoem samenvoegvelden
linktitle: Hernoem samenvoegvelden
second_title: Aspose.Words-API voor documentverwerking
description: In deze zelfstudie leert u hoe u samenvoegvelden in een document kunt hernoemen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/rename-merge-fields/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie voor het hernoemen van samenvoegvelden van Aspose.Words voor .NET. Volg elke stap zorgvuldig om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document aanmaken en de samenvoegvelden invoegen

We beginnen met het maken van een nieuw document en het gebruiken van a`DocumentBuilder` om de samenvoegvelden in te voegen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Stap 3: De naam van samenvoegvelden wijzigen

We doorlopen elk veld in het documentbereik en als het een samenvoegveld is, hernoemen we het veld door de toevoeging "_Hernoemd" achtervoegsel.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Stap 4: Het document opslaan

 Tenslotte noemen wij de`Save()` methode om het gewijzigde document op te slaan.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Broncodevoorbeeld voor het hernoemen van samenvoegvelden met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak het document en voeg de samenvoegvelden in.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Hernoem samenvoegvelden.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Bewaar het document.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Volg deze stappen om de samenvoegvelden in uw document te hernoemen met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe kan ik de naam van samengevoegde velden in een Word-document wijzigen met Aspose.Words voor .NET?

 A: Om de samengevoegde velden in een Word-document te hernoemen met Aspose.Words voor .NET, kunt u door de velden in het document lopen met behulp van de`FieldMergingArgs` klasse en gebruik de`FieldMergingArgs.FieldName` methode om veld te hernoemen.

#### Vraag: Is het mogelijk om alleen bepaalde samengevoegde velden in een Word-document te hernoemen met Aspose.Words voor .NET?

A: Ja, het is mogelijk om alleen bepaalde samengevoegde velden in een Word-document te hernoemen met Aspose.Words voor .NET. U kunt filteren welke velden u wilt hernoemen met behulp van specifieke criteria, zoals de veldnaam of andere relevante eigenschappen. Vervolgens kunt u de overeenkomstige velden hernoemen met behulp van de`FieldMergingArgs.FieldName` methode.

#### Vraag: Hoe kan ik controleren of een samengevoegd veld met succes is hernoemd in een Word-document met Aspose.Words voor .NET?

 A: Om te controleren of een samengevoegd veld succesvol is hernoemd in een Word-document met Aspose.Words voor .NET, kunt u de`FieldMergedArgs` klasse en toegang tot de`FieldMergedArgs.IsMerged` eigenschap om te bepalen of de naam van het veld met hit is gewijzigd.

#### Vraag: Wat zijn de gevolgen van het hernoemen van een samengevoegd veld in een Word-document met Aspose.Words voor .NET?

A: Wanneer u de naam van een samengevoegd veld in een Word-document wijzigt met Aspose.Words voor .NET, verandert de naam van het veld in het document, wat van invloed kan zijn op andere functionaliteit of processen die afhankelijk zijn van de veldnaam. Houd rekening met deze mogelijke gevolgen voordat u de naam van samengevoegde velden wijzigt.

#### Vraag: Is het mogelijk om de oorspronkelijke naam van een samengevoegd veld te herstellen nadat het is hernoemd met Aspose.Words voor .NET?

A: Ja, het is mogelijk om de oorspronkelijke naam van een samengevoegd veld te herstellen nadat u de naam ervan hebt gewijzigd met Aspose.Words voor .NET. U kunt de oorspronkelijke naam van het veld opslaan in een variabele of lijst, en vervolgens die informatie gebruiken om de oorspronkelijke naam indien nodig te herstellen.