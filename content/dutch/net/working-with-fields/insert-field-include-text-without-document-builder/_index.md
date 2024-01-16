---
title: Veld invoegen Tekst opnemen zonder Document Builder
linktitle: FieldIncludeText invoegen zonder Document Builder
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een FieldIncludeText-veld invoegt in uw Word-documenten met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functionaliteit "Een FieldIncludeText-veld invoegen" van Aspose.Words voor .NET. Zorg ervoor dat u elke stap zorgvuldig volgt om de gewenste resultaten te krijgen.

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

## Stap 3: Het veld FieldIncludeText invoegen

 Wij gebruiken de`AppendField()` methode om een FieldIncludeText-veld in de alinea in te voegen.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Vervolgens configureren we de eigenschappen van het veld FieldIncludeText door de naam van de bladwijzer en de naam van het bronbestand op te geven.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Vervolgens voegen we de paragraaf toe aan de hoofdtekst van het document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Tenslotte noemen wij de`Update()` methode om het veld bij te werken.

```csharp
fieldIncludeText.Update();
```

### Voorbeeld van de broncode voor het invoegen van een FieldIncludeText-veld met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak het document en de alinea.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// VeldIncludeText invoegen.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

In dit voorbeeld hebben we een nieuw document gemaakt, een alinea geïnitialiseerd, een FieldIncludeTexten ingevoegd waarin de bladwijzernaam en de naam van het bronbestand zijn opgegeven, en het document opgeslagen met een opgegeven bestandsnaam.

Dit is het einde van onze handleiding over het gebruik van de functie "Insert a FieldIncludeText" met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe kan ik het bronbestand opgeven voor het tekstopnameveld in Aspose.Words voor .NET?

 A: Om het bronbestand voor het tekstopnameveld in Aspose.Words voor .NET op te geven, kunt u de`FieldIncludeText.SourceFullName`eigenschap om het volledige pad van het bronbestand in te stellen. Zorg ervoor dat het bronbestand toegankelijk is en de inhoud bevat die u in het tekstopnameveld wilt opnemen.

#### Vraag: Kan ik tekst uit een macro opnemen in het tekstinvoegveld met Aspose.Words voor .NET?

 A: Ja, u kunt tekst uit een macro opnemen in het tekstopnameveld met Aspose.Words voor .NET. U kunt gebruik maken van de`FieldIncludeText.IncludeText` eigenschap om de naam op te geven van de macro waarvan de inhoud in het veld moet worden opgenomen.

#### Vraag: Heeft het invoegen van een tekstinclude-veld zonder de documentbuilder invloed op de Word-documentstructuur met Aspose.Words voor .NET?

A: Het invoegen van een tekstinvoegveld zonder de documentbuilder heeft geen directe invloed op de structuur van het Word-document. Het voegt echter een nieuw veldelement toe aan de documentinhoud. U kunt de documentstructuur manipuleren door de bestaande elementen toe te voegen, te verwijderen of te wijzigen, afhankelijk van uw behoeften.

#### Vraag: Kan ik de weergave van het tekstinvoegveld in een Word-document aanpassen met Aspose.Words voor .NET?

A: Het tekstopnameveld past de weergave ervan in een Word-document niet rechtstreeks aan. U kunt de opgenomen tekst echter opmaken met behulp van de alinea-eigenschappen, lettertype-eigenschappen en andere opmaakobjecten die beschikbaar zijn in Aspose.Words voor .NET.