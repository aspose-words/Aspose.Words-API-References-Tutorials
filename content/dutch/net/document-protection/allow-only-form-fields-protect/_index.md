---
title: Sta alleen formuliervelden toe in Word-document
linktitle: Sta alleen formuliervelden toe in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Aspose.Words voor .NET kunt gebruiken om Word-documenten te beschermen en alleen toe te staan dat formuliervelden worden bewerkt.
type: docs
weight: 10
url: /nl/net/document-protection/allow-only-form-fields-protect/
---
Documentbeveiliging is een essentiële functie bij het verwerken van woorden met bestanden in uw C#-toepassing. Met de Aspose.Words-bibliotheek voor .NET kunt u uw documenten eenvoudig beveiligen en alleen formuliervelden laten bewerken. In deze stapsgewijze handleiding laten we u zien hoe u de C#-broncode kunt gebruiken om alleen toe te staan dat formuliervelden worden bewerkt met behulp van de functie Alleen formuliervelden beschermen toestaan van Aspose.Words voor .NET.

## Stap 1: De documentmap instellen

De eerste stap is het definiëren van de directory van uw document. U moet het pad opgeven waar u het beveiligde document wilt opslaan. Bijvoorbeeld :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Secties en tekst invoegen

Vervolgens moet u secties en tekst in uw document invoegen. Gebruik de klasse DocumentBuilder van Aspose.Words om de inhoud van uw document op te bouwen. Hier is een eenvoudig voorbeeld:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

In dit voorbeeld maken we een nieuw, leeg document en gebruiken we DocumentBuilder om een regel tekst toe te voegen.

## Stap 3: Documentbeveiliging inschakelen

 Documentbeveiliging werkt alleen als documentbeveiliging is ingeschakeld. U kunt documentbeveiliging inschakelen met behulp van de`Protect` methode van de klasse Document. Hier is hoe:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

In dit voorbeeld schakelen we documentbeveiliging in door het beveiligingstype `

AllowOnlyFormFields` en het instellen van een wachtwoord.

## Stap 4: Alleen formuliervelden toestaan

Nu de documentbeveiliging is ingeschakeld, moeten we opgeven dat alleen het bewerken van formuliervelden is toegestaan. Dit zorgt ervoor dat gebruikers alleen delen van het document kunnen bewerken die formuliervelden zijn. Hier is hoe:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Zorg ervoor dat u "wachtwoord" vervangt door het wachtwoord dat u eerder hebt ingesteld.

## Stap 5: Het beveiligde document opslaan

 Ten slotte kunt u het beveiligde document opslaan met behulp van de`Save` methode van de klasse Document. Geef het volledige bestandspad en de gewenste bestandsnaam op. Bijvoorbeeld :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Zorg ervoor dat u "dataDir" vervangt door het pad naar uw documentmap.

### Voorbeeldbroncode voor de functie Alleen formuliervelden beveiligen met Aspose.Words voor .NET

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Voeg twee secties in met wat tekst.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Een documentbeveiliging werkt alleen als de documentbeveiliging is ingeschakeld en alleen bewerken in formuliervelden is toegestaan.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Sla het beveiligde document op.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Conclusie

In deze handleiding hebben we onderzocht hoe u de Aspose.Words-bibliotheek voor .NET kunt gebruiken om een document te beveiligen en alleen toe te staan dat formuliervelden worden bewerkt. Door de aangegeven stappen te volgen, kunt u deze functionaliteit eenvoudig in uw C#-applicatie implementeren. Documentbescherming is essentieel om de veiligheid en vertrouwelijkheid van uw documenten te garanderen.

### Veelgestelde vragen over het toestaan dat alleen formuliervelden worden beschermd in een Word-document

#### Vraag: Wat is documentbeveiliging in Aspose.Words voor .NET?

A: Documentbeveiliging in Aspose.Words voor .NET is een functie waarmee u uw documenten kunt beveiligen door bepaalde acties te beperken, zoals bewerken, opmaken of wijzigen van de inhoud. Het helpt de integriteit en vertrouwelijkheid van uw documenten te behouden door ongeoorloofde wijzigingen te voorkomen.

#### Vraag: Hoe kan ik een document beveiligen en toestaan dat alleen formuliervelden worden bewerkt met Aspose.Words voor .NET?

A: Om een document te beveiligen en toe te staan dat alleen formuliervelden worden bewerkt met Aspose.Words voor .NET, kunt u deze stappen volgen:
1. Definieer het mappad voor uw document.
2.  Voeg secties en tekst in uw document in met behulp van de`DocumentBuilder` klas.
3.  Schakel documentbeveiliging in met behulp van de`Protect` werkwijze van de`Document` class, waarbij het beveiligingstype wordt gespecificeerd als`AllowOnlyFormFields` en het verstrekken van een wachtwoord.
4.  Sla het beveiligde document op met behulp van de`Save` werkwijze van de`Document` klas.

#### Vraag: Kan ik formuliervelden in een beveiligd document invoegen met Aspose.Words voor .NET?

A: Ja, u kunt formuliervelden in een beveiligd document invoegen met Aspose.Words voor .NET. De documentbeveiliging met de`AllowOnlyFormFields` type stelt gebruikers in staat alleen de formuliervelden te bewerken terwijl de rest van de inhoud van het document wordt beschermd. U kunt gebruik maken van de`DocumentBuilder` class om formuliervelden in het document in te voegen voordat de beveiliging wordt ingeschakeld.

#### Vraag: Kan ik de documentbeveiliging van een beveiligd document verwijderen?

 A: Ja, u kunt de documentbeveiliging van een beveiligd document verwijderen met Aspose.Words voor .NET. Om de bescherming te verwijderen, kunt u de`Unprotect` werkwijze van de`Document` klasse en geef het juiste wachtwoord op. Hierdoor wordt de beveiliging opgeheven en kunt u het document onbeperkt bewerken.

#### Vraag: Is het mogelijk om een document met meerdere beveiligingstypes te beschermen?

 A: Nee, met Aspose.Words voor .NET kan slechts één beveiligingstype tegelijk op een document worden toegepast. echter, de`AllowOnlyFormFields` beveiligingstype kan het bewerken van formuliervelden effectief beperken, terwijl andere beveiligingstypen zijn toegestaan, zoals`AllowOnlyComments` of`AllowOnlyRevisions`te combineren met formulierveldbeveiliging.

#### Vraag: Kan ik verschillende wachtwoorden instellen voor verschillende beveiligingstypen in een document?

A: Nee, met Aspose.Words voor .NET kunt u één wachtwoord instellen voor documentbeveiliging, ongeacht het beveiligingstype. Hetzelfde wachtwoord wordt gebruikt om documentbeveiliging in en uit te schakelen.