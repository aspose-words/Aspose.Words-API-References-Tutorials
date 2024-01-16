---
title: Onbeperkte sectie in Word-document
linktitle: Onbeperkte sectie in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u onbeperkte secties in een Word-document definieert met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-protection/unrestricted-section/
---
In deze zelfstudie begeleiden we u bij de stappen voor het gebruik van de onbeperkte sectiefunctie van Aspose.Words voor .NET. Met deze functie kunt u specifieke secties in een Word-document definiëren die niet zijn beveiligd, zelfs als de rest van het document wel is beveiligd. Volg onderstaande stappen:

## Stap 1: Het document en de secties maken

Begin met het maken van een exemplaar van de klasse Document en een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg inhoud toe aan het document
Gebruik het DocumentBuilder-object om inhoud aan het document toe te voegen en sectie-einden in te voegen:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Stap 3: Bescherm document en secties

Sectiebeveiliging werkt alleen als documentbeveiliging is ingeschakeld en alleen bewerken in formuliervelden is toegestaan. U kunt het document beveiligen met behulp van de Protect()-methode van het Document-object:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Zorg ervoor dat u het juiste type beveiliging specificeert en het gewenste wachtwoord instelt.

## Stap 4: Beveiliging voor een specifieke sectie uitschakelen

Standaard zijn alle secties beveiligd, maar u kunt de beveiliging voor een specifieke sectie selectief uitschakelen met behulp van de eigenschap ProtectedForForms van het Section-object:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

In dit voorbeeld is de bescherming uitgeschakeld voor de eerste sectie.

## Stap 5: Sla het document op

Sla ten slotte het gewijzigde document op:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft om het document met onbeperkte secties op te slaan.

### Voorbeeldbroncode voor Unrestricted Section met Aspose.Words voor .NET

Hier is de volledige broncode voor de onbeperkte sectie met Aspose.Words voor .NET:


```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Voeg twee secties in met wat tekst.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Sectiebeveiliging werkt alleen als de documentbeveiliging is ingeschakeld en alleen bewerken in formuliervelden is toegestaan.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Standaard zijn alle secties beveiligd, maar we kunnen de beveiliging selectief uitschakelen.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Door deze stappen te volgen, kunt u eenvoudig onbeperkte secties in uw Word-document definiëren met Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we de onbeperkte sectiefunctie van Aspose.Words voor .NET onderzocht, waarmee specifieke secties in een Word-document onbeschermd kunnen blijven terwijl de rest van het document wordt beschermd. Door de gegeven stappen te volgen, kunt u eenvoudig secties binnen uw document definiëren waar gebruikers de inhoud vrijelijk kunnen bewerken terwijl de bescherming voor andere secties behouden blijft. Aspose.Words voor .NET biedt krachtige mogelijkheden voor documentbescherming en aanpassing, waardoor u controle krijgt over de bewerkingsrechten binnen uw Word-documenten.

### Veelgestelde vragen voor onbeperkte sectie in Word-document

#### Vraag: Wat zijn onbeperkte secties in Aspose.Words voor .NET?

A: Onbeperkte secties in Aspose.Words voor .NET zijn specifieke secties binnen een Word-document die niet zijn beveiligd, zelfs als de rest van het document wel is beveiligd. Met deze secties kunnen gebruikers de inhoud ervan wijzigen, terwijl de bescherming van de overige delen van het document behouden blijft.

#### Vraag: Hoe kan ik onbeperkte secties maken met Aspose.Words voor .NET?

A: Om onbeperkte secties in een Word-document te maken met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Maak een exemplaar van de`Document` klasse en een`DocumentBuilder` voorwerp.
2.  Gebruik de`DocumentBuilder` om inhoud aan het document toe te voegen en sectie-einden in te voegen.
3.  Beveilig het document met behulp van de`Protect` werkwijze van de`Document` object, met vermelding van het gewenste beveiligingstype en wachtwoord.
4.  Schakel de bescherming voor een specifieke sectie uit door de`ProtectedForForms` eigendom van de corresponderende`Section` bezwaar tegen`false`.
5. Sla het gewijzigde document op.

#### Vraag: Kan ik meerdere onbeperkte secties binnen een Word-document hebben?

 A: Ja, u kunt meerdere onbeperkte secties binnen een Word-document hebben. Door selectief de bescherming voor specifieke secties uit te schakelen met behulp van de`ProtectedForForms` eigendom van de`Section`object kunt u meerdere secties definiëren waar gebruikers de inhoud vrijelijk kunnen wijzigen terwijl andere secties beschermd blijven.

#### Q4. Kan ik de beveiliging verwijderen van een sectie die aanvankelijk beveiligd was?
 Ja, u kunt de beveiliging verwijderen van een sectie die aanvankelijk werd beveiligd door de`ProtectedForForms` eigendom van de corresponderende`Section` bezwaar tegen`false`. Hierdoor kunnen gebruikers de inhoud binnen die specifieke sectie zonder enige beperking bewerken.

#### Vraag: Welke beveiligingstypen kunnen op een Word-document worden toegepast?

A: Aspose.Words voor .NET biedt verschillende beveiligingstypen die op een Word-document kunnen worden toegepast, waaronder:
- NoProtection: Er wordt geen bescherming toegepast.
- AllowOnlyRevisions: Gebruikers kunnen alleen revisies in het document aanbrengen.
- AllowOnlyComments: Gebruikers kunnen alleen opmerkingen aan het document toevoegen.
- AllowOnlyFormFields: Gebruikers kunnen alleen formuliervelden in het document bewerken.
- Alleen-lezen: het document is alleen-lezen en bewerken is niet toegestaan.


