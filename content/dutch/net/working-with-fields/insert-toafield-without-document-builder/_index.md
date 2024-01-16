---
title: TOA-veld invoegen zonder Document Builder
linktitle: TOA-veld invoegen zonder Document Builder
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het invoegen van TOA-velden zonder Document Builder met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-toafield-without-document-builder/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie "TOA Field Insertion" van Aspose.Words voor .NET. Volg elke stap zorgvuldig om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document en de alinea maken

We beginnen met het maken van een nieuw document en het initialiseren van een paragraaf.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Stap 3: Het TA-veld invoegen

We gebruiken de klasse FieldTA om een TA-veld in de alinea in te voegen.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Stap 4: De alinea toevoegen aan de hoofdtekst van het document

We voegen de paragraaf met het TA-veld toe aan de hoofdtekst van het document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Stap 5: De alinea voor het TOA-veld maken

We maken een nieuwe paragraaf voor het TOA-veld.

```csharp
para = new Paragraph(doc);
```

## Stap 6: Het TOA-veld invoegen

We gebruiken de klasse FieldToa om een TOA-veld in de alinea in te voegen.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Stap 7: De alinea toevoegen aan de hoofdtekst van het document

We voegen de paragraaf met het TOA-veld toe aan de hoofdtekst van het document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Stap 8: TOA-veld bijwerken

 Tenslotte noemen wij de`Update()` methode om het TOA-veld bij te werken.

```csharp
fieldToa.Update();
```

### Broncodevoorbeeld voor TOA-veldinvoeging zonder Document Builder met Aspose.Words voor .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// We willen TA- en TOA-velden als volgt invoegen:
// { TA \c 1 \l "Waarde 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### Veelgestelde vragen

#### Vraag: Hoe kan ik het uiterlijk van het TOA-veld dat in het Word-document is ingevoegd, aanpassen met Aspose.Words voor .NET?

A: U kunt het uiterlijk van het ingevoegde TOA-veld aanpassen door de eigenschappen van het`FieldTOA` object om opmaakopties op te geven.

#### Vraag: Kan ik meerdere TOA-velden toevoegen aan één Word-document met Aspose.Words voor .NET?

A: Ja, u kunt meerdere TOA-velden toevoegen aan één Word-document met Aspose.Words voor .NET. Herhaal gewoon de invoegstappen voor elk veld.

#### Vraag: Hoe kan ik controleren of een TOA-veld met succes in een Word-document is ingevoegd met Aspose.Words voor .NET?

A: Om te controleren of een TOA-veld succesvol is ingevoegd, kunt u door de documentinhoud bladeren en zoeken naar TOA-veldexemplaren.

#### Vraag: Heeft het invoegen van een TOA-veld zonder DocumentBuilder invloed op de opmaak van Word-documenten met Aspose.Words voor .NET?

A: Het invoegen van een TOA-veld zonder DocumentBuilder heeft geen directe invloed op de opmaak van het Word-document. De opmaakopties voor TOA-velden kunnen echter van invloed zijn op de algehele opmaak van het document.