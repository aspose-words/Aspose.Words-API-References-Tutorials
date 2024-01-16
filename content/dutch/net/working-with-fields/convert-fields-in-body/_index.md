---
title: Velden in hoofdtekst converteren
linktitle: Velden in hoofdtekst converteren
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Aspose.Words voor .NET kunt gebruiken om paginavelden naar tekst in de hoofdtekst van een Word-document te converteren.
type: docs
weight: 10
url: /nl/net/working-with-fields/convert-fields-in-body/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u de ConvertFieldsInBody-functie van Aspose.Words voor .NET kunt gebruiken met behulp van de meegeleverde C#-broncode. Met deze functie kunt u specifieke velden in de hoofdtekst van uw document omzetten naar platte tekst, waardoor uw documenten gemakkelijker te verwerken zijn. Volg de onderstaande stappen om deze functie effectief te gebruiken.

## Stap 1: Vereisten

Voordat u begint, moet u ervoor zorgen dat u Aspose.Words voor .NET hebt geïnstalleerd en dat u een document gereed heeft om te verwerken. Zorg er ook voor dat u het mappad naar uw documenten hebt.

## Stap 2: Laad het document

Begin met het declareren van een variabele voor het pad naar uw documentenmap en gebruik vervolgens die variabele om een Document-object uit het opgegeven document te initialiseren. In ons voorbeeld heet het document "Gekoppelde velden.docx".

```csharp
// Het pad naar uw documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Stap 3: Converteer paginavelden naar platte tekst

 Nu het document is geladen, kunnen we doorgaan met de conversiestappen. Om de paginavelden naar platte tekst in de hoofdtekst van de eerste sectie te converteren, kunt u de`Range.Fields` methode om alle velden in het opgegeven bereik op te halen en vervolgens velden van het type eruit te filteren`FieldType.FieldPage` . Dan kunt u gebruik maken van de`ForEach` methode om elk veld te doorlopen en de`Unlink()` methode om het naar platte tekst te converteren.

```csharp
// Geef de juiste parameters door om de paginavelden naar platte tekst in de hoofdtekst van de eerste sectie te converteren.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Stap 4: Sla het gewijzigde document op

Nadat u de paginavelden naar platte tekst heeft omgezet, kunt u het gewijzigde document opslaan met behulp van de`Save()` methode en specificeert het pad en de naam van het uitvoerbestand. In ons voorbeeld slaan we het op als "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Sla het gewijzigde document op
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Voorbeeldbroncode voor het converteren van velden in de hoofdtekst met Aspose.Words voor .NET

Hier is het volledige broncodevoorbeeld voor het converteren van velden naar de hoofdtekst met Aspose.Words voor .NET:

```csharp
// Het pad naar uw documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Linked fields.docx");

// Geef de juiste parameters door om de paginavelden naar platte tekst in de hoofdtekst van de eerste sectie te converteren.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Veelgestelde vragen

#### Vraag: Is Aspose.Words compatibel met verschillende versies van Microsoft Word?

A: Ja, Aspose.Words is compatibel met verschillende versies van Microsoft Word, waaronder Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 en Word 2019.

#### Vraag: Kan Aspose.Words omgaan met complexe veldstructuren?

EEN: Absoluut! Aspose.Words biedt uitgebreide ondersteuning voor complexe veldstructuren, inclusief geneste velden, berekeningen en voorwaardelijke expressies. U kunt de krachtige API gebruiken om met elk type veldstructuur te werken.

#### Vraag: Ondersteunt Aspose.Words veldupdatebewerkingen?

A: Ja, met Aspose.Words kunt u velden programmatisch bijwerken. Met behulp van de API kunt u eenvoudig veldwaarden bijwerken, berekeningen vernieuwen en andere veldgerelateerde bewerkingen uitvoeren.

#### Vraag: Kan ik velden naar platte tekst converteren met Aspose.Words?

EEN: Zeker! Aspose.Words biedt methoden om velden naar platte tekst te converteren. Dit kan handig zijn als u de inhoud moet extraheren zonder enige veldgerelateerde opmaak of functionaliteit.

#### Vraag: Is het mogelijk om Word-documenten met dynamische velden te genereren met behulp van Aspose.Words?

EEN: Absoluut! Aspose.Words biedt robuuste functies om Word-documenten met dynamische velden te genereren. U kunt sjablonen maken met vooraf gedefinieerde velden en deze dynamisch vullen met gegevens, waardoor u een flexibele en efficiënte oplossing voor het genereren van documenten krijgt.